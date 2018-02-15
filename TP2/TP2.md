# TP2 Mise en place d'une ICP

## Mise en oeuvre de Microsoft Active Directory Certificate Services

### Étapes préliminaires

*Les manipulations suivantes nécessitent la présence d'un contrôleur de domaine Active Directory. Dans un premier temps vous ferez donc de votre serveur ce contrôleur de domaine. Pour cela vous créerez une nouvelle forêt. Expliquez vos manipulations.*

Nous commençons par installer    le rôle ADDS depuis le gestionnaire de serveur.

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


- *faite une demande de certificat utilisateur en générant une demande PKCS#10. Importez ensuite
cette demande dans le composant logiciel enfichable Microsoft Active Directory
Certificate Services pour la valider.*

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

## Cryptographie et messagerie électronique :

### Préparation des outils clients :

*Depuis votre AC, générez deux certificats pour deux utilisateurs :*

- *le premier servira à chiffrer des mails*

- *le second à signer des mails.*

*Installez Microsoft Outlook sur vos deux postes. Configurez un compte de messagerie et installez les deux certificats utilisateurs précédemment créés à cet effet.*

### Implémentation et tests :

*Faites des tests d'envoi de mails signés et chiffrés. Révoquez un des certificats et décrivez le résultat.*