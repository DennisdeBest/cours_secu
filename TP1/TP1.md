# TP 1 OpenSSH

## Rappels théoriques

*Rappelez le fonctionnement du chiffrement asymétrique. Expliquez comment les mécanismes de cryptographie à clef publique permettent d'assurer l'authentification.*

Chaque participant de l’échange dispose d’une paire de clefs, une publique et une privée.
Une sert à chiffrer, l’autre à déchiffrer
Le même algorithme est utilisé pour le chiffrement et le déchiffrement
Repose sur des problèmes mathématiques complexe

Ce type de chiffrement permet d'assurer l'authentification grâce au lien qui existe entre le clé privé et le clé publique. En effet un message chiffré avec une clé publique ne pourra être déchiffré que avec sa clé privé correspondante.

Si la clé privé reste bien privé on peut être sur de l'origine du message.

## Préparation du serveur

### Première connexion

*Connectez vous sur le serveur*

    ssh vagrant@dentist-data.local
    
*Créez un compte utilisateur standard*

    sudo adduser sshuser
    
*Éditez le fichier /etc/ssh/sshd_config pour faire en sorte d'interdire les connexions depuis un compte root. Vérifiez également que seul le protocole SSHv2 est accepté, dans le cas contraire modifiez le fichier de configuration en conséquence. Consultez les recommandations de l'ANSSI, quelles mesures supplémentaires pourriez vousbprendre pour renforcer la configuration de votre serveur OpenSSH ?*

Pour interdir les connexions depuis un compte root : 
    
    PermitRootLogin no
    
Pour forcer SSHv2 :

    Protocol 2

On peut également désactiver l'authentification par mot de passe

    PasswordAuthentication no
    
Quand on génère les clés, plusieurs formats sont créés. Il est prudent de supprimer la clé qui est sous la forme DSA car elle est trop faible de nos jours.
On peut également supprimer la clé ECDSA car elle n'est pas compatible partout pour ne garder que la clé RSA.
Sur le client on les supprime avec

    rm ∼/.ssh/id_dsa 
    rm ∼/.ssh/id_dsa.pub
    
Dans la configuration du fichier /etc/ssh/sshd_config on désactive les types de clés qu'on utilise pas : 

    # HostKeys for protocol version 2
    HostKey /etc/ssh/ssh_host_rsa_key
    #HostKey /etc/ssh/ssh_host_dsa_key
    #HostKey /etc/ssh/ssh_host_ecdsa_key
    #HostKey /etc/ssh/ssh_host_ed25519_key

Il est aussi recommandé d'utiliser un utilitaire comme **Fail2Ban** afin de réduire la possibilité d'attaques brute force en bannisant les addresse IP après un nombre de tentatives raté.

*A l'aide de ssh­keygen, générez l'empreinte de la clef publique de votre serveur. Conservez la sur votre poste client, ou notez la quelque part. Vous en aurez besoin plus tard.*

    ssh-keygen -lf ssh_host_rsa_key
    2048 e7:bd:6d:f8:98:9e:54:91:05:0f:98:78:07:6b:71:48 ssh_host_rsa_key.pub (RSA)

*Déconnectez vous du serveur*

    exit
    
### Seconde connexion

*Faite une première demande de connection SSH depuis le compte utilisateur que vous venez de créer.*

    ssh sshuser@dentist-data.local
    The authenticity of host 'dentist-data.local (10.0.0.18)' can't be established.
    ECDSA key fingerprint is SHA256:fNaixAtamrA634ACy+6iHDPNy4WogIAh9Rh4sELSqwU.
    Are you sure you want to continue connecting (yes/no)? 
    
L'empreinte que nous avons sauvegardé précedemment était sous la forme MD5, il est donc impossible de vérifier directement cette empreinte.
Nous allons donc demander au serveur de nous retourner l'empreinte sous la forme MD5 avec la commande

    ssh -o FingerprintHash=md5 dentist-data.local
    The authenticity of host 'dentist-data.local (10.0.0.18)' can't be established.
    ECDSA key fingerprint is MD5:e7:bd:6d:f8:98:9e:54:91:05:0f:98:78:07:6b:71:48.
    Are you sure you want to continue connecting (yes/no)?
   
*Répondez "No" à la question posée. Expliquez pourquoi le système vous pose cette question.*

    Are you sure you want to continue connecting (yes/no)? no
    Host key verification failed.

C'est la première fois qu'on se connecte en SSH à ce serveur. Le système nous demande de vérifier l'empreinte de la clé publique du serveur pour s'assurer de la légitimité du serveur. Cela permet d'éviter l'usurpation du serveur ou encore les attaques de type Man In the Middle.

*A partir de l'empreinte que vous avez conservé précédemment, vérifiez la clef publique proposée par le serveur. Si elle correspond bien vous pouvez accepter la connexion.*

L'empreinte de la clé publique du serveur correspond à celle récupéré précedemment, nous pouvons désormais accepter la connexion.

*Que va t-il se passer si vous acceptez la clef publique. Vérifiez vos affirmations, et justifiez votre réponse.*

    Warning: Permanently added 'dentist-data.local,10.0.0.18' (RSA) to the list of known hosts.

Le système ajoute le serveur ssh à la liste des serveurs connus et ne nous redemandera plus de vérifier l'empreinte dans le futur.

## Préparation du client linux

*Consultez les manpages SSH et générez la bi-clef pour votre client. Pour cela utilisez ssh­ keygen sur votre poste client*

    ssh-keygen -t rsa -b 4096 -C "ssh_majeurs@test.test"

*Générez une paire de clefs. Vous consulterez les recommandations de l'ANSSI pour choisir l'algorithme ainsi que la longueur adéquat de la clef.*

L'ANSSI recommande une taille minimale de 2048 pour RSA.
Il recommande également le ECDSA 
   
    Lorsque les clients et les serveurs SSH supportent ECDSA, son usage doit être préféré à RSA.
    
Parcontre dans mon cas la suite des outils IntelliJ comme datagrip pour la gestion de base de données n'est pas compatible ECDSA.
J'ai donc opté pour une clé RSA de 4096.

*Vérifiez que les clefs ont été correctement générées. Expliquez en détail vos manipulations.*

    ssh-keygen -y -e -f id_rsa_tp
    
Cette commande permet de récupérer la clé publique à partir de la clé privé

    ---- BEGIN SSH2 PUBLIC KEY ----
    Comment: "4096-bit RSA, converted by dennisdebest@dennisdebest-GS60-2P"
    AAAAB3NzaC1yc2EAAAADAQABAAACAQDkmV6OEeo7/Yk0rRfHBuUkho4NCn8RpFSUOI6XvJ
    ...
    
Ici nous pouvons voir l'algorithme et la longueur de la clé ainsi que la clé elle même, on peut la comparer directement avec la clé publique avec :

    ssh-keygen -y -e -f id_rsa_tp.pub
    
qui nous retourne exactement la même chose.

*SSH est extrêmement pointilleux sur la sécurité des clefs, prenez donc bien soin de configurer correctement les droits d'accès à votre clef privé. Expliquez vos choix.*

D'après les recommandations de l'ANSSI : 

    Une clé privée d’authentification hôte ne doit être lisible que par le service sshd. Sous
    Unix/Linux, cela signifie qu’elle n’est lisible que par root :
    -rw------- root:root /etc/ssh/ssh_host_rsa_key
    -rw------- root:root /etc/ssh/ssh_host_ecdsa_key
    
    Une clé privée d’authentification utilisateur ne doit être lisible que par l’utilisateur auquel
    elle est associée. Sous Unix/Linux, cela signifie :
    • que la clé privée n’est lisible que par l’utilisateur ;
    • qu’elle est protégée par un mot de passe connu seulement de l’utilisateur (voir l’option
    -p de ssh-keygen).
    
On veille donc à mettre une passphrase lors de la génération des clés et on vérifie les accès aux clés :

     Sur le serveur :
     ls -la ssh_host_rsa_key
    -rw------- 1 root root 1675 Feb  9 10:22 ssh_host_rsa_key
    
    Sur le client :
    ls -la id_rsa_tp 
    -rw------- 1 dennisdebest dennisdebest 3243 févr.  9 10:50 id_rsa_tp
    
*Consultez la manpage du serveur et expliquez à quoi sert l'option StrictModes.*

Avec StrictModes activé le serveur va vérifier les droits d'accès sur les clés à chaque connexion. Si c'est trop permisif la connection sera refusée.

*Déposez maintenant la clef publique de votre client sur le serveur dans le fichier authorized_keys. Vous pourrez utiliser scp pour cela. Vous devrez peut être modifier les fichiers de configuration du client et du serveur pour faire fonctionner tout ceci correctement. Expliquez en détail toutes vos manipulations et exposez vos résultats.*

    ssh-copy-id -i id_rsa_tp sshuser@dentist-data.local
    /usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "id_rsa_tp.pub"
    /usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
    /usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
    sshuser@dentist-data.local's password: 

    Number of key(s) added: 1

    Now try logging into the machine, with:   "ssh 'sshuser@dentist-data.local'"
    and check to make sure that only the key(s) you wanted were added.

Avec ssh-copy-id nous allons copier la clé du client (spécifier avec l'option -i) sur le serveur. Si l'opération c'est déroulé correctement nous n'aurons plus besoin d'entrer le mot de passe lors de la connection ssh.

Une fois de nouveau connecté au serveurs nous pouvons vérifier la clé dans authorized_keys :

    cat ~/.ssh/authorized_keys
    
## Préparation du client windows

*En vous inspirant des manipulations sur votre client UNIX/BSD, vous allez maintenant configurer un client Windows à l'aide de putty. Téléchargez et installez Putty.exe sur votre poste Windows. Expliquez en détail toutes vos manipulations.*

On génère le biclé avec PuTTYGen.
On sélectionne le type de clé et sa taille dans 'paramètres' et on clique qur generate. Il faut bouger la souris dans le cadre vide pour générer de l'entropie.

Une fois les clés générées la clé publique apparaît dans le cadre. Il faut copier le contenu puis dans une session SSH ouvert précédemment on va coller le contenu dans ~/.ssh/authorized-keys.

Il faut maintenant enregistrer les clés sur le disque dur afin de pouvoir s'en servir par la suite pour établir une connexion ( 'Actions' -> save private key & 'Actions' -> save public key )

Afin de pouvoir ouvrir une session SSH sans avoir a entrer son mod de passe il faut ouvrir une nouvelle session PuTTY
Dans le menu sur la droite il faut aller dans Connection -> SSH -> auth -> private key file for authentication. Ici il faut naviguer vers le fichier clé privée enregistré précedemment.

Maintenant si on reviens dans 'Session' on tape l'utilisateur et l'adresse IP de la vm dans 'HostName' (ici vagrant@192.168.56.101). On peut enregistrer ces configurations pour ne pas avoir à les refaire la prochaine fois.
Si on clique sur 'Open' la session SSH s'ouvre sans mot de passe.
