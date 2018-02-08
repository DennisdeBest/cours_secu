# TP 0

## Utilisation d'un algorithme de hachage, le SHA256

### Rappels théoriques

*Expliquez moi à quoi peut servir une fonction de hachage ? Dans le cas du téléchargement d'un
fichier sur un site internet, quel risque cela permet-il de prévenir ?*

Une fonction de hachage permet d'obtenir une valeur de longueur fixe à partir d'une donnée de valeurs quelconque. Cela permet de faire une *empreinte* d'un fichier.
Dans le cas du téléchargement d'un fichier sur internet ça permet de vérifier que le fichier téléchargé n'a pas été altéré pendant le transfert.

### Contrôle d'intégrité d'un téléchargement

*Téléchargez depuis le site internet officiel la dernière version de GNUPG pour linux.*

Je télécharge GnuPG 2.2.4 sur (https://gnupg.org/download/ ) 
ensuite sur la page (https://gnupg.org/download/integrity_check.html) je récupère le sha1 de cette version :

    732266e8888c6f41c084d043c7a0058332ff3580  gnupg-2.2.4.tar.bz2
    
*A l'aide de OpenSSL et de l'empreinte SHA1 de l'archive de GNUPG affichée sur son site officiel, vérifiez que le fichier n'a pas été altéré pendant le téléchargement. Comment avez vous procédé ? Expliquez en détail vos manipulations.*
    
J'éffectue la commande 

    openssl dgst -sha1 gnupg-2.2.4.tar.bz2

qui me renvoie 
  
    SHA1(gnupg-2.2.4.tar.bz2)= 732266e8888c6f41c084d043c7a0058332ff3580
    
On voit bien que le sha1 obtenu par openssl et le sha1 publié sur le site est le même. Le fichier est donc identique.

##Chiffrement de fichier à l'aide du chiffrement symétrique AES

### Rappels théoriques

*Rappelez moi les grands principes du chiffrement symétrique.*

Consiste à chiffrer et déchiffrer un message avec une clef secrète.
La clef est la même pour le chiffrement et le déchiffrement.
Souvent l'algorithme est le même également.
Les partenaires partagent une clef secrète.

## Chiffrement de fichier

*A partir de votre éditeur de texte favori générez un fichier simple contenant le texte de votre choix.*

    echo "texte de votre choix" > fichier_simple
    
*A l'aide de OpenSSL chiffrez le contenu de ce fichier en utilisant l'algorithme AES-256-CBC. Expliquez en détail votre manipulation. Transmettez ensuite ce fichier à votre voisin, puis la clef utilisée pour le chiffrer.*

    openssl enc -aes-256-cbc -in fichier_simple -out fichier_crypt

Il nous demande d'entrer un mot de passe pour chiffrer le fichier et de le répéter pour être sur que ça soit le bon

    enter aes-256-cbc encryption password:
    Verifying - enter aes-256-cbc encryption password:

Le mot de passe pour ce fichier est *hardPassword* 

*Votre voisin vous aura transmis un fichier chiffré. Éditez son contenu et constatez que celui-ci est bel et bien chiffré. A l'aide de la clef que vous aurez reçue avec ce fichier, déchiffrez son contenu. Expliquez en détail vos manipulations. Vérifiez avec votre voisin que le contenu que vous avez obtenu est bien celui qu'il a rédigé au départ.*

    cat fichier_crypt 
    Salted__Ͷ~6g�E7�%�v)���!J���%�����`
                                          �Ix�%  
                                       
Le fichier est bien chiffré

    openssl enc -d -aes-256-cbc -in fichier_crypt -out fichier_decrypt   
    enter aes-256-cbc decryption password:
    
Si on inspecte le fichier après avoir rentré le bon mot de passe nous obtenons bien le contenu rédigé au départ

    cat fichier_decrypt 
    texte de votre choix

## Manipulation des protocoles de chiffrement asymétrique

### Rappels théoriques

*Rappelez moi les deux applications principales du chiffrement asymétrique. Expliquez leurs principes de fonctionnement respectifs.*

Chaque participant de l’échange dispose d’une paire de clefs, une publique et une privée.
Une sert à chiffrer, l’autre à déchiffrer
Le même algorithme est utilisé pour le chiffrement et le déchiffrement
Repose sur des problèmes mathématiques complexe

Ce qui permet deux applications : 

- **chiffrement** : Le Sender chiffre le message avec la clé publique du Receiver et envoie le message. Le Receiver reçoit le message et le déchiffre avec sa clé privé. Vu que seul le receiver à accès a sa propre clé privé et que le message ne peut être chiffrer que avec sa clé publique le message ne pourra être lu que par lui.

- **Signature** : Le Sender chiffre le message avec sa propre clé privée. Le sender envoie ensuite le message et la signature au Receiver.
Le Receiver déchifre la signature avec la clé publique du Sender.
vu que la clé publique ne peut déchiffrer le message que si il a été chiffré avec la clé privé correspondante on peut être sur de l'origine du message.

### Préparation de la biclef

*Générez pour chacun d'entre vous une paire de clefs RSA 2048. Repérez le répertoire où sont stockées vos clefs, puis sauvegardez les.*

On génère la clé privé avec la commande : 

    openssl genrsa -aes256 -out private.pem 2048
    Generating RSA private key, 2048 bit long modulus
    .................................+++
    ......................+++
    e is 65537 (0x10001)
    Enter pass phrase for private.pem:
    Verifying - Enter pass phrase for private.pem:

La passphrase est *hardPasssword*

Ensuite il faut extraire la clé publique de la clé privé : 

    openssl rsa -in private.pem -outform PEM -pubout -out public.pem
    Enter pass phrase for private.pem:
    writing RSA key
    
On vérifie le fichier généré : 

    less public.pem
    -----BEGIN PUBLIC KEY-----
    MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA2pITzAG1fMncdLJIy7Nm
    5VJNTFdspLJjEooOwB1ulcnrPFNuJRGoxah8XJuUplTGC7V0fP6yWJBjX+/1Gtr5
    vMK94eHfwmgpiedkRQfpEeF5FHbnCdsvZm9K2kL+zKCBj4udnqT6IK2I+nc5sgzW
    EF2fyv+HH3OFzMr6HembLTi4DHOQImy/zWvGXBl0mthS2/BrQs+cVU+/vWDEU5bS
    s1SlOGUzNvx8dzJP6l5Pom0gcaVEJDZIAWO3rr9MjQ9UtxC6Dl9SPmC9D1e/E9Fv
    QfJJoMBDW0orsWya/E3D4JFgg/v6RzjkeEk+9CY9x9Vw4hzr6d63bAu3d4gNcMLr
    VwIDAQAB
    -----END PUBLIC KEY-----
    
*Pour communiquer avec un interlocuteur vous allez devoir transmettre une de vos clefs. De laquelle s'agit-il ? Échangez alors cette clef avec toutes les personnes avec qui vous allez vouloir communiquer.*

Nous pouvons désormais partager cette clé **publique**.

### Chiffrement et déchiffrement de fichiers

*A l'aide de la clef adéquat, chiffrez un fichier texte. Vérifiez à l'aide d'un éditeur le contenu du fichier obtenu. Transmettez le à l'un de vos interlocuteur.*

On chiffre le message avec la clé **publique** du **receiver**

    openssl rsautl -encrypt -pubin -inkey public.pem -in fichier_simple -out fichier_crypt_rsa
    
On vérifie le fichier :

    cat fichier_crypt_rsa 
    �F�rN�k�>�Y�P��f�1�7)5�:��������U��F�m�������J
                              �P"΍��#WĦ}�ր���tp��%W9��3
                                                        E���!��K��ۉj���_�����T��
    �tǽj�a�N���m�>�����|,��<����+�V]����Iw`�PS��Z킕�.    \�X��W���^*n8c�Z�t�V�\���m��ߣ*��ڦW�&�V��C�H�%
    
*Récupérez un fichier chiffré par l'un de vos interlocuteur, puis déchiffrez le.*

Pour le déchifrer le **receiver** utilise sa clé **privé**

    openssl rsautl -decrypt -inkey private.pem -in fichier_crypt_rsa -out fichier_decrypt_rsa
    Enter pass phrase for private.pem:
    
Une fois la passphrase correctement rentré nous pouvons vérifier le contenu du fichier :

    cat fichier_decrypt_rsa 
    texte de votre choix

### Signature électronique

*A l'aide de la clef adéquat, signez un fichier texte. Transmettez ce fichier et sa signature à l'un de vos interlocuteur.*

On signe le message grâce à la clé **privé** du **sender**

    openssl dgst -sha256 -sign private.pem -out fichier_simple.sha256 fichier_simple
    
ça génère le fichier fichier_simple.sha256

*Récupérez un fichier signé par un de vos interlocuteur, ainsi que sa signature, puis déchiffrez le à l'aide de la clef qu'il vous aura transmise et de la signature qu'il vous a fournie. Essayez avec la clef d'un autre interlocuteur puis avec la bonne clef.*

Si on vérifie la signature avec la mauvaise clé publique une erreur est renvoyé :

    openssl dgst -sha256 -verify other_public.pem -signature fichier_simple.sha256 fichier_simple 
    Verification Failure
    
Parcontre quand la clé publique est la bonne :

    openssl dgst -sha256 -verify public.pem -signature fichier_simple.sha256 fichier_simple 
    Verified OK

Nous pouvons donc être sûr de la source du fichier.