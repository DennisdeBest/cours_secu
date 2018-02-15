# TP2 Mise en place d'une ICP

## Mise en oeuvre de Microsoft Active Directory Certificate Services

### Étapes préliminaires

*Les manipulations suivantes nécessitent la présence d'un contrôleur de domaine Active Directory. Dans un premier temps vous ferez donc de votre serveur ce contrôleur de domaine. Pour cela vous créerez une nouvelle forêt. Expliquez vos manipulations.*

- Installation du rôle ADDS

![0_roleADDS.png](.\img\0_roleADDS.png)

- Promotion en contrôleur de domaine

![1_promouvoircontroleur.png](.\img\1_promouvoircontroleur.png)

- Création de la fôret

![2_créationForet.png](.\img\2_créationForet.png)


### Installation des composants

*Avant de pouvoir commencer vous allez devoir installer et configurer votre ICP.
Pour cela installez et configurez les composants et rôles suivants sur votre serveur*

- *Active Directory Certificate Services :
Votre AC aura les caractéristiques suivantes :*
    - *AC entreprise. Expliquez la différence entre une AC entreprise et une AC autonome.*
    - *AC racine*

- *le service Certificate Authority Web Enrollment et IIS.*

## Découverte de Microsoft Active Directory Certificate Services2

### Le composant logiciel enfichable Microsoft Active Directory Certificate Services

*Expliquez ce que vous permet de faire exactement ce composant ? Manipulez ce composant pour vous
familiariser avec et découvrir les options qui vous sont proposées. Dans cette partie vous ne générerez pas
encore de certificat.*

### L'outil en ligne de commande certutil.exe3

*Cet outil vous permet scripter de nombreuses actions proposées par les interfaces graphiques de votre ICP.
Consultez la documentation et expliquez son rôle.
Pour chaque manipulation du TP, vous essaierez de voir si une option de certutil.exe permet de faire
la même chose. Si oui, vous utiliserez cet outil et vous documenterez vos manipulations.*

## Génération de requête de certificats :

### Utilisation du service Certificate Authority Web Enrollment :

*Expliquez ce que vous permet de faire cette interface exactement ?*

#### Demande de certificat depuis l'interface Web4 :

*Vous allez maintenant générer vos premiers certificats. Pour cela vous allez utiliser deux méthodes
différentes proposées par l'interface Web Enrollment*

- *faite une demande complète pour un certificat utilisateur directement depuis l'interface Web. Retournez ensuite sur votre autorité de certification et validez cette demande. Vérifiez, dans le composant logiciel enfichable des certificats, la présence du certificat que vous venez de générer.*


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


- *Familiarisez vous avec la création des templates, puis créez votre propre template. A l'aide de la méthode de votre choix5, générez un nouveau certificat à partir du template que vous venez de créer.*

## La révocation des certificats :

*Révoquez un certificat précédemment généré. Vérifiez que la révocation a bien été prise en compte par votre AC. Pour cela vous consulterez la liste des certificats révoqués du composant logiciel enfichable Microsoft Active Directory Certificate Services,*
#### La CRL :
- *Qu'est ce qu'une CRL ?*


- *Sur les ICP Microsoft, quels sont les deux modes de fonctionnement proposés pour les CRL ?*


- *Configurez la CRL de votre ICP*


- *Déployez votre CRL sur les postes clients.*


### Le service Online Responder et le protocole OCSP6 :

*Expliquez ce qu'est le service Online Responder. Installez ce service sur votre ICP, configurez le et testez le.*

## Sauvegarde et restauration des certificats et des clefs7

*Quels sont les outils mis à disposition par l'ICP Microsoft pour gérer la sauvegarde et la restauration des certificats et des clefs ? Mettez en oeuvre cette solution.*

## Cryptographie et messagerie électronique :

### Préparation des outils clients :

*Depuis votre AC, générez deux certificats pour deux utilisateurs :*

- *le premier servira à chiffrer des mails*

- *le second à signer des mails.*

*Installez Microsoft Outlook sur vos deux postes. Configurez un compte de messagerie et installez les deux certificats utilisateurs précédemment créés à cet effet.*

### Implémentation et tests :

*Faites des tests d'envoi de mails signés et chiffrés. Révoquez un des certificats et décrivez le résultat.*