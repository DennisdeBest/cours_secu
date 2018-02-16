# TP2 Mise en place d'une ICP

## Mise en oeuvre de Microsoft Active Directory Certificate Services

### Étapes préliminaires

*Les manipulations suivantes nécessitent la présence d'un contrôleur de domaine Active Directory. Dans un premier temps vous ferez donc de votre serveur ce contrôleur de domaine. Pour cela vous créerez une nouvelle forêt. Expliquez vos manipulations.*

Nous commençons par installer le rôle ADDS depuis le gestionnaire de serveur.

- Installation du rôle ADDS

![0_roleADDS.png](.\img\0_roleADDS.png)

- Promotion en contrôleur de domaine

![1_promouvoircontroleur.png](.\img\1_promouvoircontroleur.png)

- Création de la fôret

![2_créationForet.png](.\img\2_créationForet.png)

- Choix du mot de passe

![3_mdp.png](.\img\3_mdp.png)


### Installation des composants

*Avant de pouvoir commencer vous allez devoir installer et configurer votre ICP.
Pour cela installez et configurez les composants et rôles suivants sur votre serveur*

On install le rôle **Service de certificats Active Directory**
![4_serviceCertif.png](.\img\4_serviceCertif.png)

Ensuite il faut activer le service d'**inscription de l'autorité de certification via le Web**
![5_certifenregristrement.png](.\img\5_certifenregristrement.png)

- *Active Directory Certificate Services :
Votre AC aura les caractéristiques suivantes :*

*AC entreprise. Expliquez la différence entre une AC entreprise et une AC autonome.*

![6_certifDentreprise.png](.\img\6_certifDentreprise.png)

*AC racine*

![7_autoritéRacin.png](.\img\7_autoritéRacin.png)

Ensuite nous choissisons l'option pour générer une nouvelle clé privé.

![8_clé.png](.\img\8_clé.png)

Pour être conforme aux recommandations de l'ANSSI nous avons choisi une clé RSA de 2048 bits et le SHA256 comme algorithme de hachage.

![9_algo.png](.\img\9_algo.png)

- *le service Certificate Authority Web Enrollment et IIS.*

//TODO

## Découverte de Microsoft Active Directory Certificate Services

### Le composant logiciel enfichable Microsoft Active Directory Certificate Services

*Expliquez ce que vous permet de faire exactement ce composant ? Manipulez ce composant pour vous
familiariser avec et découvrir les options qui vous sont proposées. Dans cette partie vous ne générerez pas
encore de certificat.*

C'est un rôle du serveur qui permet la mise en place d'une ICP.
Il permet la génération des certificats de sécurité à l'intérieur du domaine et évite de faire appel à un tiers pour la gestion de ces certificats.

//TODO

### L'outil en ligne de commande certutil.exe

*Cet outil vous permet scripter de nombreuses actions proposées par les interfaces graphiques de votre ICP.
Consultez la documentation et expliquez son rôle.
Pour chaque manipulation du TP, vous essaierez de voir si une option de certutil.exe permet de faire
la même chose. Si oui, vous utiliserez cet outil et vous documenterez vos manipulations.*

Dans la documentation windows nous retrouvons

    Certutil.exe is a command-line program that is installed as part of Certificate Services. You can use Certutil.exe to dump and display certification authority (CA) configuration information, configure Certificate Services, backup and restore CA components, and verify certificates, key pairs, and certificate chains.

C'est donc un outil en ligne de commande qui permet de voir la configuration de l'autorité de certification ou encore de la configurer.
Cela permet également de vérifier les certificats, chaines de certificats et les biclés.
Enfin cet outil sert à faire des backups ou de restauration depuis un backup des différents composants de l'autorité de certification

## Génération de requête de certificats :

### Utilisation du service Certificate Authority Web Enrollment :

*Expliquez ce que vous permet de faire cette interface exactement ?*

web browser and see an interactive web site that allows them to upload requests, download completed certificates, and download certificate revocation lists (CRLs).

Il permet aux clients d'avoir accès à un site web interactif qui leur permet d'uploader des requêtes PKCS #10, télécharger des certificats et des LRC.

#### Demande de certificat depuis l'interface Web :

*Vous allez maintenant générer vos premiers certificats. Pour cela vous allez utiliser deux méthodes
différentes proposées par l'interface Web Enrollment*

Afin de pouvoir accéder au service de certification web il faut que les deux machines soient sur le même domaine.
Pour ce faire il faut configurer le DNS client avec l'addresse IP du contrôleur de domaine.


![10_DNS.png](.\img\10_DNS.png)

Nous pouvons ensuite rajouter le client au domaine.

![11_domaine.png](.\img\11_domaine.png)

- *faite une demande complète pour un certificat utilisateur directement depuis l'interface Web. Retournez ensuite sur votre autorité de certification et validez cette demande. Vérifiez, dans le composant logiciel enfichable des certificats, la présence du certificat que vous venez de générer.*

Sur le client, dans le navigateur, nous nous rendons sur la page [domaine]/certsrv

![12_webenroll.png](.\img\12_webenroll.png)

Ensuite nous allons cliquer sur le lien **Demander un certificat**

![13_webenroll2.png](.\img\13_webenroll2.png)

Nous avons l'erreur suivante :

![14_webenrollError.png](.\img\14_webenrollError.png)

Il nous faut donc un certificat SSL signé par l'autorité de certification. Il faut commencer par faire la demande de certificat.
![15_ssl.png](.\img\15_ssl.png)

Une fois toutes les informations fournie un fichier texte contenant la demande est enregistré.
Nous pouvons vérifier la demande avec la commande :

    certutil .\ssl_webenroll.txt

Ce qui nous montre que la demande est bien généré

    Demande de certificat PKCS10 :
    Version : 1
    Objet:
        CN=secu2018
        OU=secu
        O=secu2018
        L=secu
        S=secu
        C=FR
      Hachage du nom (sha1) : 565b7e9886c31ac70fbc68f028ab0a8a81a4179a
      Hachage du nom (md5) : 4373cba2f005e07ee00dff8486affa57

    Algorithme de clé publique :
        ID d'objet Algorithme: 1.2.840.113549.1.1.1 RSA (RSA_SIGN)
        Paramètres de l'algorithme :
        05 00
    Longueur de la clé publique : 2048 bits
    Clé publique : bits inutilisés = 0
        0000  30 82 01 0a 02 82 01 01  00 a2 81 ba 10 34 da 2f
        0010  42 27 e2 ac 45 b2 85 44  3c 97 95 cf d7 da 20 dc
        0020  fc bb 1c c5 4b b0 a2 91  88 1a b6 be a9 8c d8 53
        0030  9e 48 2d ef 42 8a 3b 04  a6 68 2c 12 5c f4 3e 24
        0040  05 6a 9c 8a ab b1 ba ac  9f 81 87 b3 97 25 b5 1c
        0050  b0 68 a2 1c 2a 3d 10 a7  2e f8 82 42 cb a6 da f7
        0060  db a0 bc 8b 16 d6 f0 38  36 97 ea 8f fb 2c 62 f3
        0070  4a ee 19 de 0b 42 34 c4  07 d2 74 ef 05 5d 63 b6
        0080  f5 f3 bc 24 bc 73 8b 54  0a 67 9b 90 a0 04 f7 0b
        0090  ca 7a 47 21 a8 47 55 74  1d ba 74 f3 bc fe a3 b3
        00a0  cc 09 5a 20 3d d2 07 5d  23 a9 94 57 5e 4c 57 48
        00b0  2a bf 60 73 05 a4 2c 17  e5 0c 72 17 c1 f0 bf f3
        00c0  64 af e2 00 da 5b 26 a8  6e ce d8 81 50 9c 30 57
        00d0  46 b9 b4 87 9f 3f 8d dd  f4 fe 80 56 8f 2c 3c 4c
        00e0  6a 1a db 8f 21 8c c2 ad  03 c2 db bb fb 4d 39 89
        00f0  33 3f ca 85 eb 1f b4 da  12 06 f7 6c 03 5f 19 3f
        0100  5e e3 81 2a 52 92 fa c5  5b 02 03 01 00 01
    Attributs de la demande : 4
      4 attributs :

      Attribut[0]: 1.3.6.1.4.1.311.13.2.3 (Version du système)
        Valeur[0][0], Longueur = c
            6.2.9200.2

      Attribut[1]: 1.3.6.1.4.1.311.21.20 (Informations sur le client)
        Valeur[1][0], Longueur = 49
        Type d'attribut inconnu
        ID du client : = 5
        ClientIdDefaultRequest -- 5
        Utilisateur : SECU2018\Administrateur
        Ordinateur : WIN-Q8J7UEAEIAB.SECU2018.com
        Processus : inetmgr.exe

      Attribut[2]: 1.3.6.1.4.1.311.13.2.2 (Fournisseur de services de chiffrement d'inscription)
        Valeur[2][0], Longueur = 64
        Type d'attribut inconnu
        Information concernant le fournisseur de services de chiffrement
        KeySpec = 1
        Fournisseur = Microsoft RSA SChannel Cryptographic Provider
        Signature : bits non utilisés = 0

      Attribut[3]: 1.2.840.113549.1.9.14 (Extensions de certificat)
        Valeur[3][0], Longueur = c1
        Type d'attribut inconnu
    Extensions de certificat : 4
        2.5.29.15 : indicateurs = 1(Critique), longueur = 4
        Utilisation de la clé
            Signature numérique, Non-répudiation, Chiffrement de la clé, Chiffrement des données (f0)

        2.5.29.37 : indicateurs = 0, longueur = c
        Utilisation avancée de la clé
            Authentification du serveur (1.3.6.1.5.5.7.3.1)

        1.2.840.113549.1.9.15 : indicateurs = 0, longueur = 6b
        Capacités SMIME
            [1]Capacité SMIME
                 ID de l'objet=1.2.840.113549.3.2
                 Paramètres=02 02 00 80
            [2]Capacité SMIME
                 ID de l'objet=1.2.840.113549.3.4
                 Paramètres=02 02 00 80
            [3]Capacité SMIME
                 ID de l'objet=2.16.840.1.101.3.4.1.42
            [4]Capacité SMIME
                 ID de l'objet=2.16.840.1.101.3.4.1.45
            [5]Capacité SMIME
                 ID de l'objet=2.16.840.1.101.3.4.1.2
            [6]Capacité SMIME
                 ID de l'objet=2.16.840.1.101.3.4.1.5
            [7]Capacité SMIME
                 ID de l'objet=1.3.14.3.2.7
            [8]Capacité SMIME
                 ID de l'objet=1.2.840.113549.3.7

        2.5.29.14 : indicateurs = 0, longueur = 16
        Identificateur de la clé du sujet
            02 2a 7c ae 1d fb 81 a6 65 47 e0 75 d0 1c ee 62 9d 5d fc 7c

    Algorithme de signature :
        ID d'objet Algorithme: 1.2.840.113549.1.1.5 sha1RSA
        Paramètres de l'algorithme :
        05 00
    Signature : bits non utilisés = 0
        0000  c3 be ad 4b b5 0c e7 8e  5a e7 50 a8 b6 e0 e7 ef
        0010  26 be d5 bd bc 02 f5 6a  2b 6a 1b e3 84 3f f3 a7
        0020  22 56 44 c6 77 23 84 32  01 bb 9e 6c c9 94 a5 e5
        0030  73 fd 66 7e e1 82 e8 c0  16 1e ab 99 59 e0 e2 fd
        0040  10 02 12 e5 40 7b 27 b1  4d c1 2a 2e 25 9c 5f de
        0050  47 f9 33 6e 67 05 42 c2  fc 2e fd 95 1f d8 f4 d3
        0060  c9 c9 25 11 cb 9f 10 f9  86 9e 40 49 8d 36 03 23
        0070  a1 9a 1f ce 41 ee 8c 7e  ec 37 2f e2 4f 19 e5 d5
        0080  84 41 4b ef 4e e6 88 7c  9f 93 b2 06 0d a6 01 58
        0090  19 c5 43 5f 7c 8b 63 18  03 0c 2a 94 26 9d a4 95
        00a0  6e fa ab 54 35 9d 5a 57  80 c9 c6 2c f4 f8 81 06
        00b0  f1 28 a2 b3 62 86 ed d4  e6 f6 ac ac f6 42 4b 94
        00c0  83 0b 82 b5 9e 9c a0 a4  bc 83 2d 2b be 39 4e a3
        00d0  89 3c 0d b6 9b 85 78 d9  c0 d2 d0 d7 de 70 65 1d
        00e0  17 30 42 db 1f 14 b5 cb  86 58 93 0f ef 47 e9 a8
        00f0  f4 c0 93 d2 05 67 af 10  9d 17 78 67 7c a1 e3 29
    La signature correspond à la clé publique
    Hachage de l'identificateur de clé (rfc-sha1) : 02 2a 7c ae 1d fb 81 a6 65 47 e0 75 d0 1c ee 62 9d 5d fc 7c
    Hachage de l'identificateur de clé (sha1) : 06 81 8e 52 9b 9e 10 5e 59 00 d1 8d 39 b6 4d e0 1d ca 2f ed
    CertUtil: -dump La commande s'est terminée correctement.

Ensuite il faut soumettre cette demande de certification à l'autorité de certification avec la commande

    certreq -submit ./ssl_webenroll.txt

![16_certreq.png](.\img\16_certreq.png)

Nous obtenons à nouveau une erreur

![17_ssl_cert_error.png](.\img\17_ssl_cert_error.png)

Dans notre demande il n'y a pas l'attribut de demande **CertificateTemplate**, L'autorité de certification ne sait donc pas quel type de certificat délivrer.

Nous allons donc refaire une requête, à la main cette fois-ci. Donc avec le bloc-notes nous allons créer le fichier .inf suivant :

    [Version]
    Signature="$Windows NT$"

    [NewRequest]
    Subject = "CN=*.SECU2018.COM"   ; For a wildcard use "CN=*.CONTOSO.COM" for example
    ; For an empty subject use the following line instead or remove the Subject line entierely
    ; Subject =
    Exportable = FALSE                  ; Private key is not exportable
    KeyLength = 2048                    ; Common key sizes: 512, 1024, 2048, 4096, 8192, 16384
    KeySpec = 1                         ; AT_KEYEXCHANGE
    KeyUsage = 0xA0                     ; Digital Signature, Key Encipherment
    MachineKeySet = True                ; The key belongs to the local computer account
    ProviderName = "Microsoft RSA SChannel Cryptographic Provider"
    ProviderType = 12
    SMIME = FALSE
    RequestType = CMC

    ; At least certreq.exe shipping with Windows Vista/Server 2008 is required to interpret the [Strings] and [Extensions] sections below

    [Strings]
    szOID_SUBJECT_ALT_NAME2 = "2.5.29.17"
    szOID_ENHANCED_KEY_USAGE = "2.5.29.37"
    szOID_PKIX_KP_SERVER_AUTH = "1.3.6.1.5.5.7.3.1"
    szOID_PKIX_KP_CLIENT_AUTH = "1.3.6.1.5.5.7.3.2"

    [Extensions]
    %szOID_SUBJECT_ALT_NAME2% = "{text}dns=secu2018.com"
    %szOID_ENHANCED_KEY_USAGE% = "{text}%szOID_PKIX_KP_SERVER_AUTH%,%szOID_PKIX_KP_CLIENT_AUTH%"

    [RequestAttributes]
    CertificateTemplate= WebServer

On voit bien l'attribut CertificateTemplate à la fin du fichier.
Nous allons convertir ce fichier .inf en .req avec la commande

     certreq -new .\manual_ssl_cert.inf .\manual_ssl_cert.req

Nous pouvons maintenant soumettre cette demande et générer le certificat.

    certreq -submit ./manual_ssl_cert.req

Nous allons maintenant finaliser la demande de certificat dans le serveur IIS.
Ensuite il faut activer le SSL et choisir le certificat que nous venons de créer en allant dans les options du site web puis dans liaisons.

![23_terminer_la_demande.png](.\img\23_terminer_la_demande.png)

![24_terminer2.png](.\img\24_terminer2.png)

Et enfin on fait la liaison avec le certificat.

![25_liaison.png](.\img\25_liaison.png)

Une fois le SSL en place nous pouvons retourné sur l'interface web pour finir la demande de certificat utilisateur.

![30_submit_auto_user_cert_req.png](.\img\30_submit_auto_user_cert_req.png)

Le certificat est généré automatiquement par l'AC et nous pouvons l'installer.


- *faite une demande de certificat utilisateur en générant une demande PKCS#10. Importez ensuite
cette demande dans le composant logiciel enfichable Microsoft Active Directory
Certificate Services pour la valider.*

Il faut d'abord désactiver l'acceptation auto des certificats.

![26_accept_auto.png](.\img\26_accept_auto.png)

Ensuite nous fesons la demande de certificat PKCS10.

![22_pkcs10user.png](.\img\22_pkcs10user.png)

![27_certificat_pending.png](.\img\27_certificat_pending.png)

Si nous retournons sur l'aurité de certification nous voyons le certificat en attente.

![28_certificate_pending2.png](.\img\28_certificate_pending2.png)

Il s'avère que nous avions mal compris la consigne, il faut générer le certificat pkcs10 sous forme de fichier et ensuite l'ajouter manuellement dans le serveur.

Tout comme pour la génération du certificat SSL précédemment nous allons utiliser l'outil certreq dans powershell pour générer le fichier PKCS10 à partir du fichier .inf.

    [Version]
    Signature="$Windows NT$"

    [NewRequest]
    Subject = "CN=Administrateur&CN=Users&DC=SECU2018&DC=com"
    Exportable = FALSE                  
    KeyLength = 2048                    
    KeySpec = 1                         
    KeyUsage = 0xA0                     
    MachineKeySet = True               
    ProviderName = "Microsoft RSA SChannel Cryptographic Provider"
    ProviderType = 12
    SMIME = FALSE
    RequestType = PKCS10

    [Strings]
    szOID_SUBJECT_ALT_NAME2 = "2.5.29.17"
    szOID_ENHANCED_KEY_USAGE = "2.5.29.37"
    szOID_PKIX_KP_SERVER_AUTH = "1.3.6.1.5.5.7.3.1"
    szOID_PKIX_KP_CLIENT_AUTH = "1.3.6.1.5.5.7.3.2"

    [RequestAttributes]
    CertificateTemplate= User
.

    certreq -new .\user_cert.inf .\user_cert.req

Ensuite nous utlisons à nouveau certutil pour vérifier le format du fichier .req

    PS C:\Users\Administrateur\Documents> certutil .\user_cert.req
    Demande de certificat PKCS10 :
    Version : 1
    Objet:
        CN=Administrateur&CN=Users&DC=SECU2018&DC=com
      Hachage du nom (sha1) : 92d910cceeeafc1c4f2765e1de0cebe425c98bc8
      Hachage du nom (md5) : f955735e8bc877becb6268894498b049

    Algorithme de clé publique :
        ID d'objet Algorithme: 1.2.840.113549.1.1.1 RSA (RSA_SIGN)
        Paramètres de l'algorithme :
        05 00
    Longueur de la clé publique : 2048 bits
    Clé publique : bits inutilisés = 0
        0000  30 82 01 0a 02 82 01 01  00 89 8c 92 71 31 05 e6
        0010  10 36 b6 31 b8 15 a3 e9  1c 4c 88 da 77 22 bf c7
        0020  a4 5e be 38 34 8f ab 99  26 2f 59 15 ff 75 e7 20
        0030  a9 33 7a 78 28 ea 65 4d  ad d6 cc 6f 15 04 44 7b
        0040  3c b2 ed 05 cc dd f2 82  3f 28 e1 1f 66 87 22 da
        0050  55 57 0c f1 91 51 db 6c  24 c2 51 e9 be d2 c9 5b
        0060  b1 a2 88 bb 3e b0 cb fb  da 62 65 bd 4f 95 cb 8d
        0070  b6 0a ed 12 52 27 e1 7d  45 04 14 63 91 42 c3 79
        0080  ef 09 09 9e 1a 28 2a de  6f cb a1 7e 51 9e 12 97
        0090  76 28 d5 d4 55 ca 39 56  cb 3a 76 78 95 9a d2 8b
        00a0  02 e0 90 84 a0 17 4c 1f  15 36 d8 7f 7d b3 33 8a
        00b0  1f 42 fe 4f ea 41 ba 23  6c e0 14 c4 cc de c4 9a
        00c0  56 ab 5b 02 04 fe 9d 1f  47 66 7f 0c 6f d0 cb 59
        00d0  66 18 07 07 88 40 5b 2b  d7 f4 04 61 bf 3c 55 00
        00e0  3e 01 e5 42 c0 22 1b f0  01 9d bd 53 ee 69 9a 44
        00f0  39 47 0e c4 9b a2 99 4d  ff d3 52 9c 22 19 b8 75
        0100  b1 d3 f7 94 00 03 b2 85  2f 02 03 01 00 01
    Attributs de la demande : 5
      5 attributs :

      Attribut[0]: 1.3.6.1.4.1.311.13.2.3 (Version du système)
        Valeur[0][0], Longueur = c
            6.2.9200.2

      Attribut[1]: 1.3.6.1.4.1.311.13.2.1 (Paire de valeurs de noms d'inscription)
        Valeur[1][0], Longueur = 34
            CertificateTemplate=User

      Attribut[2]: 1.3.6.1.4.1.311.21.20 (Informations sur le client)
        Valeur[2][0], Longueur = 49
        Type d'attribut inconnu
        ID du client : = 9
        ClientIdCertReq -- 9
        Utilisateur : SECU2018\Administrateur
        Ordinateur : WIN-Q8J7UEAEIAB.SECU2018.com
        Processus : certreq.exe

      Attribut[3]: 1.3.6.1.4.1.311.13.2.2 (Fournisseur de services de chiffrement d'inscription)
        Valeur[3][0], Longueur = 64
        Type d'attribut inconnu
        Information concernant le fournisseur de services de chiffrement
        KeySpec = 1
        Fournisseur = Microsoft RSA SChannel Cryptographic Provider
        Signature : bits non utilisés = 0

      Attribut[4]: 1.2.840.113549.1.9.14 (Extensions de certificat)
        Valeur[4][0], Longueur = 75
        Type d'attribut inconnu
    Extensions de certificat : 4
        1.3.6.1.4.1.311.20.2 : indicateurs = 0, longueur = a
        Nom du Modèle de certificat (Type de certificat)
            User

        2.5.29.37 : indicateurs = 0, longueur = 22
        Utilisation avancée de la clé
            Système de fichiers EFS (Encrypting File System) (1.3.6.1.4.1.311.10.3.4)
            Messagerie électronique sécurisée (1.3.6.1.5.5.7.3.4)
            Authentification du client (1.3.6.1.5.5.7.3.2)

        2.5.29.15 : indicateurs = 1(Critique), longueur = 4
        Utilisation de la clé
            Signature numérique, Chiffrement de la clé (a0)

        2.5.29.14 : indicateurs = 0, longueur = 16
        Identificateur de la clé du sujet
            70 08 80 fc 13 f9 6a bb 7d 0c 3f 31 bb de d3 64 c3 79 28 c8

    Algorithme de signature :
        ID d'objet Algorithme: 1.2.840.113549.1.1.5 sha1RSA
        Paramètres de l'algorithme :
        05 00
    Signature : bits non utilisés = 0
        0000  e7 f5 18 dd cd be f9 95  fc f6 51 e8 b7 0f fc 88
        0010  24 d5 3b ea bf c4 c2 30  be d1 50 fc f9 92 65 6c
        0020  c7 f9 81 76 e7 ab da 52  b1 76 4c 99 cf 58 4c 1b
        0030  7e ca 5b 63 ae f5 25 85  31 2d ad a9 eb 7f 88 7e
        0040  97 47 f2 13 de 61 58 c5  36 c0 fa b0 ec 69 e4 15
        0050  47 fc 2c 6d a6 f2 62 6a  c8 af 96 e6 56 f1 c0 94
        0060  15 4b b5 2d cd 03 35 8b  1c d7 78 a4 46 e2 d8 f0
        0070  af cf 3e f0 09 3d b2 79  45 cb 2c f5 3f cc 8d d5
        0080  6c f0 4e c3 01 b9 0f bc  4a 88 2d 88 8f c4 20 c5
        0090  6a 56 08 cb f8 56 c2 e6  e7 8e 4a ec 7b 2b ca 3c
        00a0  b2 5f ce 16 f6 93 83 ca  17 75 26 eb 0d 9c 94 e9
        00b0  d3 df f1 1b 08 59 49 2d  c3 2c 00 6b 1c 7c 03 31
        00c0  0c 53 bc 89 dc 22 c8 4e  52 c0 a4 80 d3 70 9c bc
        00d0  a1 69 a7 7d ed 4e f1 f0  a9 d8 80 a7 85 a6 d5 a1
        00e0  f2 8f 09 87 04 c5 65 a5  0f 81 6e 8a e0 e9 db 40
        00f0  4c 3f 70 92 fd 1f 19 af  00 78 87 f3 57 df 86 13
    La signature correspond à la clé publique
    Hachage de l'identificateur de clé (rfc-sha1) : 70 08 80 fc 13 f9 6a bb 7d 0c 3f 31 bb de d3 64 c3 79 28 c8
    Hachage de l'identificateur de clé (sha1) : 66 c6 cb 2b 58 72 c1 43 7f bf 5b 09 61 84 8a 69 47 ff 7a ea
    CertUtil: -dump La commande s'est terminée correctement.

Il s'agit bien d'un fichier au format PKCS10.

Nous allons donc prendre ce fichier encodé en base 64 et le copier dans l'interface web.

![31_base64_pkcs10.png](.\img\31_base64_pkcs10.png)

![32_base64_pkcs10_2.png](.\img\32_base64_pkcs10_2.png)

#### Utilisation du service Certificate Authority Auto Enrollment :

*Expliquez le rôle et le fonctionnement de l'auto enrollment de votre AC. Mettez en oeuvre cette nouvelle
fonctionnalité. Vous testerez son bon fonctionnement en ajoutant un utilisateur ou un ordinateur à votre
Active Directory.*

#### Industrialisation de la génération des certificats : les templates

*L'ICP Microsoft vous permet de créer des templates de certificats.*

- *Quelle est l'utilité de cette fonctionnalité ?*


- *Familiarisez vous avec la création des templates, puis créez votre propre template. A l'aide de la méthode de votre choix, générez un nouveau certificat à partir du template que vous venez de créer.*

## La révocation des certificats :

*Révoquez un certificat précédemment généré. Vérifiez que la révocation a bien été prise en compte par votre AC. Pour cela vous consulterez la liste des certificats révoqués du composant logiciel enfichable Microsoft Active Directory Certificate Services,*
#### La CRL :
- *Qu'est ce qu'une CRL ?*


- *Sur les ICP Microsoft, quels sont les deux modes de fonctionnement proposés pour les CRL ?*


- *Configurez la CRL de votre ICP*


- *Déployez votre CRL sur les postes clients.*


### Le service Online Responder et le protocole OCSP :

*Expliquez ce qu'est le service Online Responder. Installez ce service sur votre ICP, configurez le et testez le.*

## Sauvegarde et restauration des certificats et des clefs

*Quels sont les outils mis à disposition par l'ICP Microsoft pour gérer la sauvegarde et la restauration des certificats et des clefs ? Mettez en oeuvre cette solution.*

La sauvegarde peut se faire depuis la fenêtre d'administration de l'autorité de certification :

![29_sauvegarde.png](.\img\29_sauvegarde.png)

Nous pouvons également utiliser certutil en ligne de commande :

     -backup           -- Sauvegarder les Services de certificats Active Directory
     -backupDB         -- Sauvegarder la base de données des Services
                          de certificats Active Directory
     -backupKey        -- Sauvegarder le certificat et la clé privée
                          des Services de certificats Active Directory
     -restore          -- Restaurer les Services de certificats Active Directory
     -restoreDB        -- Restaurer la base de données des Services de certificats
                          Active Directory
     -restoreKey       -- Restaurer le certificat et la clé privée des Services
                          de certificats Active Directory

## Cryptographie et messagerie électronique :

### Préparation des outils clients :

*Depuis votre AC, générez deux certificats pour deux utilisateurs :*

- *le premier servira à chiffrer des mails*

- *le second à signer des mails.*

*Installez Microsoft Outlook sur vos deux postes. Configurez un compte de messagerie et installez les deux certificats utilisateurs précédemment créés à cet effet.*

### Implémentation et tests :

*Faites des tests d'envoi de mails signés et chiffrés. Révoquez un des certificats et décrivez le résultat.*