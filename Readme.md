# Sécurité des SI


[TOC]



jeudi, 01. février 2018

- Mettre en place SMSI système de gestion de la sécu norme iso 27001

## Domaines

#### Audits :
- Architecture : Comment est conçu le système, recherche de failles, de SPOF ...
- Configuration des équipements (switchs, routeurs ...)
- Code
- Organisationnel, problème dans le processus de dévelopment par exemple (manque d'automatisation pendant les MEP)

#### Tests d'intrusions (PenTest)

#### Conseils
Assister les clients en amont, acoompagnement pour la rédaction du cahier des charges sécurité

#### Expertises techniques
Reforcement de configurations, ajouts de sécu dans des applications, ...

#### Réponse à incident
Gestion de crises, investigations numériques

## Bonnes pratiques

Les normes iso 27000 

- 27001 : Comment construire un SMSI
- 27002 : Guide de bonnes pratiques
- 27005 : Gestions de risques

OWASP : Open Web Application Security Project
Consortium mondiale pour la sécurité applicative
TOP 10 : les 10 vulns les + exploitées du moment

Méthode [EBIOS](https://www.ssi.gouv.fr/guide/ebios-2010-expression-des-besoins-et-identification-des-objectifs-de-securite/)  d'analyse de risque

#### A propos d'[ISO](https://www.iso.org/home.html)
International Standardization Organization, Les normes sont des spécifications de premier order pour les produits, services et bonne pratiques dans une optique e qualité, sécurité et efficacité.
Facilite le commerce international.

## Cybercriminalité

Terme qui désigne l'ensemble des infractions pénales susceptibles de ce commetre sur les réseaux de télécommunications ou ciblant ces réseaux.

- Les infractions spécifiques aux technologies de l'information (TIC) parmis lesquelles les atteintes aux système de traitement automatiques de données (STAD) sont sanctionnées par l' [article 323.1](https://www.legifrance.gouv.fr/affichCodeArticle.do?idArticle=LEGIARTI000006418316&cidTexte=LEGITEXT000006070719) et suivants du code pénal (le fait d'accéder au de se maintenir frauduleusement dans un système de données est passible de 2 ans d'emprisonnement et 60 000€, en cas d'altération c'est 3 ans et 100 000€ d'amendes, 5ans et 150 000€ si contre un système de l'état).

- Les infractions dont la commision est liée ou facilité par l'alteration des TIC parmis lesquelles :
    - les atteintes au mineurs ([article 227.3](https://www.legifrance.gouv.fr/affichCodeArticle.do?cidTexte=LEGITEXT000006070719&idArticle=LEGIARTI000033460756) )
    - les infractions à la loi sur la presse (loi du 29/07/1981)
    - les atteintes au personnes (usurpations d'identités ...)
    - les escroqueries (phishing, fausse lotteries, utilisation frauduleuse de moyens de paiement, ...)


## L'[ANSSI](https://ssi.gouv.fr)  (Agence Nationale pour la sécurité des SI)

Ils ont développés un [MOOC](https://www.ssi.gouv.fr/actualite/secnumacademie-le-nouvelle-formation-en-ligne-met-la-cybersecurite-a-la-portee-de-tous/). Leur rôle est de promouvoir la sécurité auprès du publiques et des entreprises.
Protégé les systèmes de l'état, controler les OIV

#### OIV (Opérateur d'importance Vitale)
Certains hopitaux (pour les soins des VIPS du gouvernement), opérateurs de téléphones, ...

#### PSSIE (Politique de sécurité de SI de l'état)
Analyse de risques ...

#### RGS (Référentiel général de la sécurité)
Normes imposés par l'état

# Introduction à la sécurité des SI

- **Le système d'information** est un ensemble organisé de ressources (matériels, logiciel, personel, procédures, ...) qui permet de regrouper, classifier, traiter et diffuser de l'information sur un environnement donné.

- **La sécurité du SI** c'est l'ensemble des moyens techniques, juridiques, organisationelles nécéssaires et mises en places pour conserver, rétablir et garantir la confidentialité, l'intégrité et la disponibilté du SI

- **Les critères de sécurité** 

    - La confidentialité : garantir l'accès à l'information uniquement aux entités **autorisés**
    - l'intégrité : garantir l'**exactitude** et l'**exhaustivité** des données
    - la disponibilité : garantir l'**accès** et l'**utilisation** à la demande de l'information pour une etité autorisé
 
    Ces critères sont pondérés selon les besoins.
    
## Assurer la sécurité, comment ?

- Il faut appliquer les pricipes de sécurisation à tous les niveaux. C'est à dire sur toutes les composantes du périmètre qu'on étudie. C'est le concept de **Défense en profondeur** .
- Le risque nul et la sécu a 100% n'existent pas
- il n'existe pas de solutions génériques, tout dépend du contexte

Il faut avoir une liste claire des **actifs** (tout ce qui à de la valeru pour un entité et qui nécéssite par conséquent une protection)  :

 - les actifs primordiaux, impalpables, inhérent à l'existence même de l'entité, les activités de l'entités
 - les actifs en support, physiques, permette la réalisation des actifs primordiaux
 
 **Vulnérabilites** : faille dans un **actif**, un **groupe d'actifs** ou une **mesure de sécurité**
 Ajouter une mesure de sécurité augmente également la surface d'attaque (ex: un plugin pour la sécu dans un CMS)
 
 **Menace**: Cause potentiel d'un évenement indésirable. (ex: un orage)
 
**Scénario d'incident**: L'actif possède des vulnérabilités, la menance exploite une vulnérabilité et ainsi cible un actif.
La probabilité que le scénario se produise est la **vraisemeblance**.
Une fois le scénario produits il y a la **conséquence**, résultat d'un évenement indésirable.
**L'impact** est un changement rédicale des objectifs métiers atteints.

L'ensemble des ces éléments représentes le **risque**. On peut réduire le risque en agissant sur ces différents éléments.

**Rique résiduel** risque qui subside après le traitement du risque.47741

#### Lectures associées

- [Management de la sécurité du SI](https://www.abebooks.fr/9782212138146/2212138148/plp)  d'Alexandre Fernandez Torro (4ème édition en avril 2018) ISBN : 9782212138146
- [Gestion des risques en sécurité de l'information](https://www.abebooks.fr/9782212134797/Gestion-risques-s%C3%A9curit%C3%A9-linformation-Mise-2212134797/plp), ISO 27005, ISBN : 9782212134797
- [Sécurité opérationelle](https://www.abebooks.fr/9782212144604/S%C3%A9curit%C3%A9-op%C3%A9rationnelle-Conseils-pratiques-s%C3%A9curiser-2212144601/plp), ISBN: 9782212144604

# Présentation des systèmes de management
SMSI, SMSSI, SGSI
C'est un système où on centralise les informations, une organisation mis en place pour gérer les éléments sur lesquels on travaille.

- Issue du vocabulaire de la qualité (ISO 9000)
- Le système de management est une organisation que l'on met en place qui permet de définir une politique, des objectifs et d'atteindre les objectifs.
- c'est un ensemble de mesures techniques et organisationnelles visant a atteindre des objectifs et une fois les objectifs atteinds, les maintenirs voir les dépasser.
- quelques normes : 
    - ISO 9001 => qualité
    - ISO 14001 => l'environnement
    - ISO 20000 => L'informatique (pas la sécurité)
    - ISO 22000 => Alimentaire
    - ISO 27001 => la sécu des SI
    
Les apports de la mise en oeuvre d'un système de management, sachant que c'est une opération complexe, couteuse en temps et en ressources.

- Permet à l'entreprise d'adopter des bonnes pratiques
- Augmente le fiabilité
- meilleure image auprès des clients
    
Ces systèmes sont basés sur l'amélioration continue

- Roue de deming : Plan Do Check Act

## ISO 27001

C'est un document d'une trentaine de pages.
Les 5 premiers chapitres : Présentation de la norme et du SMSI
les 4 suivants : Exigences

- le SMSI est adaptable à toutes les types d'activités et toutes les tailles d'entrprise.
- Mettre en oeuvre, exploiter et améliorer un SMSI documenté

C'est une norme volontairement assez vague.

## Les grandes étapes du SMSI
### PLAN

#### analyse du risque ISO 27005
**Définition de la politique et du périmètre** : étape cruciale, la suite vient s'appuyer sur ce qui a été défini ici. Le périmètre c'est le champ d'appréciation de l'étude et la politique c'est le niveau de sécurité exigé

**Appréciation du risque** : Identifier le risque et l'évalué, Il est possible d'utiliser la méthode d'analyse de risque de son choix.
L'appréciation du risque selon ISO 27005 : 

- Etablissement du contexte
- appréciation du risque
- traitement du risque
- Acceptation du risque
- Traitement du risque
- Sélection des mesures de sécu

Comment identifier et évaluer le risque ?
**Identifier** :

- recenser les actifs (il peut être judicieux de les cartographiers)
- lister les vulnérabilités
- lister les menaces
- lister les mesures de sécu

<table><tr><th>actifs</th><th>vuln</th><th>menaces</th><th>mesures</th></tr>
<tr><td>Firewall</td><td>pas redondé</td><td>panne</td><td></td></tr>
<tr><td>Firewall</td><td>firmwarepas a jour</td><td>code malveillant, exploit de vuln</td><td></td></tr>
<tr><td>Firewall</td><td>fin du support</td><td>panne</td><td></td></tr>
</table>

Ensuite il faut créer des échelles de valeurs pour pondérés chacun des composants du risque sur une échelle de 1 à 4

<table><tr><th>Valeur</th><th>Signification</th></tr>
<tr><td>1</td><td>Actif facilement remplaçable, couts faible ( > 1000 € )</td></tr>
<tr><td>4</td><td>Temps de remplacement long (+ d'un moins) coût d'achat élevé</td></tr>
</table>

**Tableau de valorisation des menaces**

<table>
<tr><th>valeur</th><th>Signification</th></tr>
<tr><td>1 improbable</td><td>Très peu de chance d'arriver</td></tr>
<tr><td>3 certain</td><td>se produit régulièrement</td></tr>
</table>

On pondère actif, vuln, menaces, mesures de sécurité ainsi que la vraisemblance et les conséquences

<table>
<tr><th>Vraisemblance</th><th>1</th><th>2</th><th>3</th></tr>
<tr><th>Conséquence</th>
	<td><table><tr><th>1</th><th>2</th><th>3</th></tr></table></td>
	<td><table><tr><th>1</th><th>2</th><th>3</th></tr></table></td>
	<td><table><tr><th>1</th><th>2</th><th>3</th></tr></table></td>
</tr>
<tr><th>Valeur de l'actif<table>
<tr><th>1</th></tr>
<tr><th>2</th></tr>
<tr><th>3</th></tr>
<tr><th>4</th></tr>
<tr><th>5</th></tr>
<tr><th>6</th></tr>
<tr><th>7</th></tr>
</table></th>
<td>
<table>
<tr><td>2</td><td>3</td><td>4</td></tr>
<tr><td>3</td><td>4</td><td>5</td></tr>
<tr><td>4</td><td>5</td><td>6</td></tr>
<tr><td>5</td><td>6</td><td>7</td></tr>
<tr><td>6</td><td>7</td><td>8</td></tr>
<tr><td>7</td><td>8</td><td>9</td></tr>
<tr><td>8</td><td>9</td><td>10</td></tr>
</table>
</td>
<td>
<table>
<tr><td>3</td><td>4</td><td>5</td></tr>
<tr><td>4</td><td>5</td><td>6</td></tr>
<tr><td>5</td><td>6</td><td>7</td></tr>
<tr><td>6</td><td>7</td><td>8</td></tr>
<tr><td>7</td><td>8</td><td>9</td></tr>
<tr><td>8</td><td>9</td><td>10</td></tr>
<tr><td>9</td><td>10</td><td>11</td></tr>
</table>
</td>
<td>
<table>
<tr><td>4</td><td>5</td><td>6</td></tr>
<tr><td>5</td><td>6</td><td>7</td></tr>
<tr><td>6</td><td>7</td><td>8</td></tr>
<tr><td>7</td><td>8</td><td>9</td></tr>
<tr><td>8</td><td>9</td><td>10</td></tr>
<tr><td>9</td><td>10</td><td>11</td></tr>
<tr><td>10</td><td>11</td><td>12</td></tr>
</table>
</td>
</table>

#### Triatement du risque

Choisir le mode de traitement a appliquer parmis les 4 suivants :

- Réduction du risque: prendre des mesures pour faire chuter la valeur du scénario d'incident
- Evitement: on décide ne pas faire l'activité à risque
- Transfert: 
    - externaliser l'activité a risque
    - Prendre une assurance
- l'acceptation: on décide de ne rien faire, on accepte ce risque

Une fois la méthode de traitement choisi on construit le tableau "plan de traitement du risque" 
On utilise ISO 27002 pour construire la déclaration d'applicabilité (dda, en anglais c'est Statement Of applicability).

### DO

- Mettre en oeuvre les mesures de sécurité
- mettre en place des indicateurs (entre autres pour mesurer l'efficacité des mesurer)
- former et sensibiliser le personnel
- Gestion de la sécurité au quotidien
- Gérer les incidents de sécurité ISO 27035

### CHECK

On va controler que le SMSI est efficace et qu'il est conforme aux spécifications, il y a pour cela 3 outils :
- audits intenes
- controles internes
- revues

**audits internes** : C'est un audit planifié, réalisé sur une clause précise de l'ISO.
Les utilisateurs et opérateurs sont informé de l'audite.
Il est réalisé par une personne interne à l'entité mais qui n'a pas participé à la mise en place des mesures.

**Controle interne**: Il s'agit la de vérifier de façon inopiné que les mesures de sécu sont correctement appliquées. L'effet de surprise est importante

**Revues**: 

- Revues ponctuels: Parfois il peut être nécéssaire de faire une revue sans attendre la prochaine revue de direction (en cas de changement dans l'entreprise, en cas d'incident de sécurité)
- Revues de direction: 
    - revues périodiques, au moins une fois par an
    - faire le point sur les résultats des audites internes
    - permet d'avoir un retour des différents acteurs
    - point sur les actions en cours
    - point sur les menaces auquels on n'avait pas pensé lors de l'analyse de risque
    - interpreter les indicateurs
    - définir les nouvelles priorités
    - changements survenue dans l'organisation à prendre en compte
    
### ACT

Il va probablement falloir intervenir sur le SMSI pour corriger les écarts

 - Actions préventives
 - Actions correctives
 - Actions d'amélioration
 
 **Actions préventives**: On a détecté une situation à risque qui pourrait provoquer des écarts/incidents par rapport aux objectifs fixés. Il va falloir agir sur les causes.
 
 **Actions correctives**: Un incident s'est produit, un écart a été constaté. On agi d'abord sur les conséquences et ensuite sur les causes pour éviter que le scénario se reproduise.
 
 **Actions d'amélioration**: une mesure de sécu est en place, fonctionne, mais n'est pas suffisament performante
 
 ---
 
 jeudi, 08. février 2018
 
# Les concepts fondamentaux de la cryptographie appliquée 

#### ressources

- Applied cryptography, Bruce Schneier [@schneierblog](https://twitter.com/schneierblog) , ISBN 9781119096726, [https://schneier.com](https://schneier.com) 
- Serious Cryptography, Jean-philippe Aumasson [@veorq](https://twitter.com/veorq) , ISBN 9781593278267, [https://131002.net](https://131002.net) 
- Cryptographie quantique, Renaud Lifchitz [@nono2357](https://twitter.com/nono2357) , [https://www.nolimitsecu.fr/informatique-quantique](https://www.nolimitsecu.fr/informatique-quantique) 

## Qu'es ce que la cryptographie
C'est un sous ensemble de la cryptologie, 
<table><tr><th>Cryptologie</th></tr><tr><th><table><th>Cryptographie</th><th>Cryptanalyse</th></tr></table></th></tr></table>

## A quoi ça sert ?

- Authentification
- Intégrité
- Confidentialité
- Non-répudiation : Empecher quelqu'un de nier d'avoir fait quelquechose.

### Vocabulaire

#### Les acteurs de la cryptographie

- L'utilisateur (Users)
    - Expéditeur (Sender)
    - Destinataire (Receiver)
- le cryptographe (Cryptographers)
- le cryptanalyste (Crypanalysts)

#### La notion de message et de chiffrement

- message clair (Plaintext)
- Message chiffré (Ciphertext)
- chiffrement (Encryption)
- déchiffrement (Decryption) (!= décryptage !)

#### Les algorithmes cryptographiques

- Cryptographic alorithm
- Cipher

#### One-time Pad

- Clefs cryptographiques à une seule utilisation
- Clef de même longueur que le message
- Technique de chiffrement parfaite si :
    - La clef n'est effectivement utilisée qu'une seule fois ET
    - Qu'elle est générée de façon parfaitement aléatoire.
    
# Les principaux systèmes cryptographiques

## Les fonctions de hachage (One Way Hash Function)

- Fonction de prise d'empreinte numériques
- A partir d'une donée quelconque (pre-image) l'algorithme génère une donnée :
    - De longueur fixe
    - représentative de la donnée initiale
    - on appelle cette donnée **h** empreinte (Hash)
    
Si deux données différentes ont des Hash identiques on parle de **collision**.
Le hashage est à sens unique, il est impossible de retrouver la valeur de départ avec le hash.
Renforcement par l'utilisationde sel (**salt**).

### Pricipaux algorithmes
- MD5 (Message Digest Algorithm) : 32chars 128bits
- SHA (Secure Hash Algorithm) : 
    - SHA1, il commence à y avoir des collisions 40chars 160bits
    - SHA256, 64chars 256bits
    
### Extension des fonctions de hachage

- MAC (Message Authentication Code)
    - Génération d'une valeur souvent appelé **tag**
    - le tag sert à authentifier le message.
    - il garant son intégrité et son authenticité
    - génération d'une clef secrète partagée.
    - signature du message avec la clef.
    - Vérification de la signature à l'aide du message, du tag et de la clef
- HMAC (Keyed-Message Authentication Code)
    - Génération d'une clef secrète dérivée ensuite pour générer deux secrets.
    - Deux passes de fonction de hachage salées par ces deux secrets
    - nom de l'algo : HMAC-{Fonction_de_hachage} ex: HMAC-SHA1
    
## La cryptographie symétrique

Consiste à chiffrer et déchiffrer un message avec une clef secrète.
La clef est la même ainsi que l'algo.
Les partenaires partagent une clef secète.

### Le différents types d'alorithmes

#### Algorithme de chiffrement par flux (Stream Ciphers)
 Message à chiffrer de longueur quelconque
 Chiffrement bit par bit ou octet par octet (dans certains cas par mot de 32 bits)
 Génération d'une valeur pseudo aléatoire appelée **Keystream** à partir d'une flec (**seed**)
 **Keystream** est ensuite utilisé pour chiffrer les données (en général avec l'opération binaire XOR)
 IV + key = seed
 Ex d'utilisation: WEP, WPA
 Algorithmes symétriques par flux : RC4, SEAL, utilisé dans PKZIP
#### Algorithme de chiffrement par Block (Block Ciphers)
 Message à chiffrer de longueur quelconque
 Message découpé en blocs de taille fixe
 Le dernier bloc peut être comblé pour atteindre la taille du bloc (**padding**)
 Chaque bloc claire donnera toujours le même bloc chiffré
 On peut traiter les blocs de différentes façon, modes d'opération:
 
 -  ECB (Electronic Codebook): il ne faut plus l'utiliser, trop faible.
 - CBC (Cipher Block Chainig): Le plus utilisé, utilise le block chiffré précedent comme vecteur d'initialisation du block suivant.
 - CFB (Cipher Feedback): C'est l'IV qui est chiffré, il est XOR avec le plaintext et c'est utilisé comme IV du block suivant.
 - OFB (Output Feedback): C'est l'IV chiffré qui est utilisé comme IV du block suivant
 
### A propos du Vecteur d'initialisation (IV)

Bloc de données aléatoire utilisé pour démarrer le chiffrement du premier bloc
Ajoute une notion de hasard au chiffrement
**Ne pas utliser le même IV avec deux clefs différents !**
Pas nécéssaire de chiffrer l'IV par contre :

- Sa génération doit être aléatoire
- L'ensemble des IV doit être sufficamment grand

#### Principaux algorithmes symétriques par blocs : 

- DES, 3DES (Data Encryption Standard) **a bannir**
- AES (Advanced Encryption Standard)
- IDEA 
- Blowfish
- SAFER

**Il est recommandé d'utiliser AES-256-CBC**

### A quoi sert la cryptographie symétrique
Authentification
Confidentialité

## La cryptographie asymétrique (à clef publique)

### Principe de fonctionnement

Chaque participant de l'échange dispose d'une paire de clefs, une publique et une privée.
Une sert à chiffrer, l'autre à déchiffrer
Le même algorithme est utilisé pour le chiffrement et le déchiffrement
Repose sur des problèmes mathématiques complexes :

- factorisation d'un nombre entier formé de grands facteurs premiers
- résolution d'un logarithme discret sur un corps fini
- résolution d'un logarithme discret sur une courbe elliptique

Deux applications :

- chiffrement
_ex_: Alice chiffre son message avec la clé publique de Bob, Alice envoie le message chiffré à Bob, Bob déchiffre le message avec sa propre clé publique.
- signature électronique
_ex_: Alice chiffre son message avec sa propre clef privée, Alice envoie le message ainsi que la signature à Bob, Bob déchiffre la signature avec la clef publique d'alice.

#### Principaux algorithmes asymétriques:

- RSA (Rivest Shamir Adleman)
- ElGamal
- Système à courbes élliptiques
- DSA (Digital Signature Algorithm) (uniquement pour la signature électronique)

**Il est recommandé d'utiliser RSA avec des clefs de 2048 bits**

##### Example de fonctionnement RSA

Fondé en 1977 par Ron Rivest, Adi Shamir et Leonard Adleman, basé sur la complexité de factoriser des grands nombre (problématique calculatoire).

Un exemple avec de petits nombres premiers (en pratique il faut de très grands nombres premiers) :

    on choisit deux nombres premiers p = 3, q = 11 ;
    leur produit n = 3 × 11 = 33 est le module de chiffrement ;
    φ(n) = (3 – 1) × (11 – 1) = 2 × 10 = 20 ;
    on choisit e= 3 (premier avec 20) comme exposant de chiffrement ;
    l'exposant de déchiffrement est d = 7, l'inverse de 3 modulo 20 (en effet ed = 3 × 7 ≡ 1 mod 20).

La clé publique d'Alice est (n, e) = (33, 3), et sa clé privée est (n, d) = (33, 7). Bob transmet un message à Alice.

    Chiffrement de M = 4 par Bob avec la clé publique d'Alice : 43 ≡ 31 mod 33, le chiffré est C = 31 que Bob transmet à Alice ;
    Déchiffrement de C = 31 par Alice avec sa clé privée : 317 ≡ 4 mod 33, Alice retrouve le message initial M = 4.

Le mécanisme de signature par Alice, à l'aide de sa clé privée, est analogue, en échangeant les clés.

### A quoi sert la cryptographie asymétrique

---

Vendredi, 09. février 2018

## Définition d'un ICP (Infrastructure à clefs publiques) et des ses acteurs

Comment garantir l'authenticité de la clef publique ?

-> Faire intervenir un tiers de confiance :
    
    L'autorité de certification
    
### Qu'es ce qu'un infractructure à clés publiques ?

- Infrastructure a clés publiques : **ICP**
- Infrastructure de Gestion des clés : **IDC**
- Public Key Infrastructure : **PKI**

#### Lectures associées

- T. Autret, L. Bellefin, M-l Oble-Laffaire, sécuriser ses échanges électroniques avec une PKI (ISBN 2212110456)

#### Définition

Une ICP c'est :
"Un ensemble de composants physiques (des ordinateurs, des équipements cryptographiques logiciels ou matériel type HSM ou encore des cartes à puces), de procédures humaines (vérifications, validation) et de logiciels (système et application) destiné à gérer les clés publiques des utilisateurs d'un système."

#### De quelle façon

- Loren kohnfelder (1978) mentionne pour la première fois dans sa thèse : "un ensemble de données contenant un nom et une clé publique signé numériquement"
- par l'introduction de la notion de certificat électronique

## Le certificat électronique

### Qu'es ce que c'est qu'un certificat électronique

Document électronique qui conteint des données publiques
Garantie l'autenticité de la clé publique qu'il contient
Permet à Bob d'être sur que la clé publique qu'il utilise appartient bien à Alice.

La clé publique contenu par le certificat permettra de chiffrer des données et/ou vérifier une signature électronique.
Pour remplir sa fonction un certificat doit :

- être propre à l'entité pour laquelle il a été créé
- permettre à l'utilisateur de trouver l'identité de cette entité
- contenir la clé publique
- présenter de manière claire l'autorité qui garantie son contenu
- être infalsifiable
- présenter de manière claire sa période de validité
- indiquer l'utilisation qui peut être faite de la clé de publique qu'il contient
- porter un numéro d'identification

#### A propos de cryptographie à clé publique ou **PKCS** (Public-Key Cryptography Standards)

- Une quizaine de standards
- Développés par les labos RSA
- Permette de faciliter l'implémentation de la cryptographie à clé publiques
- parmi lesquels PKCS#7 (façon de représenter les données dans les fichiers), PKCS#10 (représente les requêtes de demandes de génération de certificats), PKCS#12 (représentes les clés publiques/privés dans un seul fichier, surtout sous windows)

#### Formats des fichiers de certificats

- **.pem** (Privacy-enhanced Electronic Mail) : certificat DEF encodé en base 64, encadré par les mentions "----BEGIN CERTIFICATE----" et "-----END CERTIFICATE-----"
- **.cer, .crt, .der** : Certificat **DER** au format binaire
- **.p7b, p7c** (PKCS#7) contient plusieurs certificats ou CRL(s) (Certificate Revocation List)
- **.p12** (PKCS#12) contient un bloc contenant la clé privée et certificat.

#### Le format x509

- Créé en 1988
- Le plus utilisé aujourd'hui
- propose un standard pour la structure des certificats

(en PHP -> PHPKi utilise la lib openSSL pour générer des PKI)

Un certificat x509 contient

- Des champs standars
- Des champs d'extensions (type, criticité et valeur)
    - 4 types : Informations sur les clés, informations sur l'utilisation du certificat, attributs sur les utilisateurs e les AC, Co-contraines de certifications
    - Criticité : Flag 0 ou 1, si 1 et que l'application n'est pas capable de répondre à cette exigence alors il ne pourra pas utiliser le certificat

Certificate Fields :

- Champs standards
    - Version
    - Numéro de série
    - Certificate Signature Algorithme : L'algorithme de hachage utilisé pour faire l'empreinte des informations du certificat ainsi que l'algorithme de chiffrement.
    - Issuer : Celui qui délivre le certificat
    - Validity : Période de validité du certificat 'not before' & 'not after'
    - Subject : La cible du certificat (porteur)
    - Subject Public Key Info : Algorithme et contenu de la clé publiqe du porteur
    - Signature de l'AC

- Champs d'estensions :
    - Certificate Key Usage: critical / Siging / Key Encipherment
    - Extended Key Usage: not critical / ...
    - ...

### Les acteurs d'une ICP

- L'utilisateur du certificat, il va récupérer le certificat du **sujet** pour utiliser la clé publique qu'il contient
- Le **Subject** (détenteur du certificat), possède un biclé et veut que celle-ci soit "certifiée" par un tiers de confiance
- L'infracstructure de confiance
    - **L'autorité de certification**, génère le certificat et le signe, délivre les supports (physiques)
    - L'autorité d'Enregistrement, récolte les infos sur le porteur de la biclé (futur subject) et vérifie que les infos soient correctes
    - Le service de publication, un endroit ou publie les certificats
    - Le dépôt de la LCR, une liste qui contient les numéros de séries des certificats qui ne sont plus valides
    - L'Autorité d'horodatage, emet le timestamp
    - L'Autorité de Validation

Jeudi, 15. février 2018

## Cycle de vie d'un certificat

### La phase d'initialisation

- Enregistrement d'une demande
- Authentification d'une demande
- Génération du certificat (et éventuellement de la biclé)
- Distribution/Publication du certificat (et la clé privée si génération de la biclé)

### La phase d'utilisation

- Vérification du statut du certificat
- "Extraction" de la clé publique
- Utilisation de la clé publique

### La phase de révocation ou de suspension

- Enregistrement d'une demande de révocation ou de suspension
- Révocation du certificat
- Suspension du certificat
- Revalidation d'un certificat suspendu

### La phase de renouvellement

- Enregistrement d'une demande de renouvellement
- Renouvellement du certificat
- Publication et distribution du certificat

## Le processus de création d'un certificat

Le sujet contacte l'authorité d'enregistrement (**AE**) et peut éventuellement demander la génération d'une biclé (à éviter).
L'AE retourne une liste d'info à fournir au sujet. Le niveau de justificatifs demandé dépend de l'utilisation qui va être faite du certificat. Elle vérifie que le porteur détends bien la clé privé (elle envoie un challenge chiffré avec la clé publique du sujet qu'il doit déchiffrer à l'aide de sa clé privée).

L'AE transmet la demande de création à l'autorité de certification (**AC**), elle génère le certificat à partir des informations de l'AE.
Une fois le certificat généré l'AC va signer le certificat avec sa clé privé, ensuite il se peut que le certificat soit publié dans le dépôt.

l'AC transmet le certificat a l'AE qui le fourni au sujet. Le sujet peut désormais installer le certificat pour permettre son utilisation.

### Les fonctions de l'AC lors de la création

- Génération et signature du certificat
- Publication du certificat (si nécessaire)

### Les fonctions de l'AE lors de la création

- Enregistrement de la demande
    - Authentificattion du demandeur
    - Vérification des attributs
- Distribution du certificat (et éventuellement de la clé privée correspondante)

## Le procssus de révocation

Un certificat n'est pas détruit.

### Pour quelles raisons révoquer un certificat ?

- Suspicion ou compromission effective de la clé privée
- Modification des informations contenues dans le certificat
- Dysfonctionnement du support physique (ou perte des données d'activation)
- Un changement de l'état de l'art de la cryptographie

Un certificat expiré n'est pas révoquer, il est déja inutilisable.

Le sujet demande la révocation a l'AE et il transmet le numéro de série du certificat et le motif de la révocation.
L'AE enregistre la demande et vérifie que le demandeur est habillité à demander la révocation.
l'AE transmet la demande à l'AC.
l'AC répercute la révocation dans le service de publication.

### L'AC répercute la révocation ?
- Deux façons de procéder
    - Révocation par publication d'un annuaire positif (on l'enlève de la liste blanche)
    - Révocation par publication de listes négatives
        - Liste de certificats révoqués (LCR)
        - Certificat Revocation List (CRL)

### A propos des LCR

- Liste contenant les numéros de séries des certificats révoqués
- Signées par l'AC
- Format x509v2 le plus utilisé
- Publié à intervalle régulier par l'AC

#### Optimisation des LCR

- Taille des LCR rapidement contraignant
- Utilisation de CRL Distribution point
- Publication de Deltas CRL

#### Format d'une LCR x509v2

- Version (CRL Format Version)
- Algorithme utilisé pour signer la CRL
- Nom de l'émetteur de la CRL
- Date d'émission
- Date d'émission de la prochaine
- La clé publique
- Liste des certificats révoqués (numéros de séries)
- Signature de l'AC

## Le processus de validation

### Quand à lieu la validation ?

- Au cours de la phase d'utilisation
- Juste avant l'utilisation de la clé publique
- Réalisée de manière automatique par l'application utilisatrice.
- Un contrôle manuel peut être nécéssaire (cas particulier)

### Pricipales étapes

- Contrôle de l'intégrité du certificat (vérification de l'empreinte)
- Côntrole de la validité (date, chemin de certification, état du certificat)
- Côntrole de la politique d'usage du certificat

### Comment controler l'état du certificat ?

- Mise en oeuvre de la LCR
- Mise en oeuvre d'une **Autorité de Validation**
    - Utilisation du protocol **OCSP** (Online Certificate Status Protocol)

## Les modèles de confiance

Le domaine de confiance : Les certificats sont émis et utilisable dans un périmètre donnée.

### Les différents modèles

- ICP privée (ou fermée)
- ICP en réseau
- ICP ouverte

ICP = Infrastructure à clé publique = PKI

#### Les ICP privées

- Mise en oeuvre pour les besoins internes d'une entité
- Le domaine de confiance est limité à l'entité
    - Seuls les utilisateurs internes à l'entité peuvent échanger en toute confiance
    - Les certificats émis en interne ne sont pas reconnus de confiance en dehors de l'entité.

#### Les ICP en réseau

- Plusieurs ICP privées ont besoin de communiquer entre elles
- Problèmatique : 
    - Les certificats ne sont reconnus de confiance que dans les entités qui les ont créées.
- Le domaine de confiance doit s'étendre aux différents entités.

Entité A qui possède sa propre ICP dans laquelle elle à sa propre AC, pareil pour l'entité B. Qui doivent communiquer entre eux c'est par exemple le cas pour une fusion ou un rachat d'entreprises.

1. Création d'une autre ICP qui délivre les certificats des AC A et B du coup les certificats ne sont plus autosigné mais signé par l'AC AB et du coup on reste dans le domaine de confiance.
2. L'AC d'une des entités devient l'AC racine et refait les certificats de l'autre enttité.
3. Certification croisés (cross certificate pair), champs particulier qui dis que le certificat a été géneré par des AC croisés, les deux AC sont reconnus de confiance.

### Les ICP ouvertes

- C'est le modèle utilisé sur internet aujourd'hui
- Tout le monde peut communiquer avec tout le monde
- Les certificats des utilisateurs sont délivrés par des opérateurs privés
    - Niveau de confiance limité

## Les différentes architectures

### Architecture simples

- les architectures plates,
- La Liste de certificats de confiance

### Architectures évoluées

- Les architectures hiérarchiques, plusieurs AC, une racine et des filles.
- Les architectures hybrides, les cas de la certification croisée.

Dans le cas des certificats croisés si il y a trop d'AC on met en place une AC centrale qui dispatch les demandes de certification (Point focal)

vendredi, 23. février 2018

# La sécurité des systèmes nomades

## Qu'es ce qu'un système nomade ?

C'est une ressource su SI qui va être utilisée en dehors du périmètre de sécurité du SI

- Ordinateur portables
- smartphone tablettes
- poste de travail fixedans le cadre du télétravail
- périphériques de stockage(clé USB, disque dur, ...)

Il y a des risques spécifiques aux équipements nomades. Ces risques sont bien identifiés, et des mesures spécifiques ont été prévues dans ISO27002 :

- chapitre 9.2.5 Sécurité du matériel hors des locaux.
- chapitre 11.7 Informatique mobile et télétravail.

Il convient de mettre en oeuvre différents types de mesures :

- Protection physique
- Cryptographiques
- Des contrôles d'accès
- Définir une politique particulière

### A propos des risques :

#### Risque pour le système nomade

- Vol du matériel, peut porter atteinte à la disponibilité et à la confidentialité des données
- Déterioration du matériel
- Infection du matériel, peut porter atteinte à la sécurité du SI

####Risques pour le SI

- Infection
- Intrusion par usurpation d'identité

## Renforcer les aspects physiques

- Renforcer la sensibilisation des utilisateurs (cf guide de l'ANSSI passeport de conseil aux voyageurs)
    - Avant le départ
    - Pendant la mission
    - Avant le retour de mission
    - Après la mission

### Avant de partir en mission

- Rappeler aux utilisateurs de relire les consignes et les règles de  sécurité établi par l'entreprise
- Se renseigner sur la législation locale
- Utiliser que du matériel dédié uniquement à la mission
- Sauvegarder les données avant le départ
- Eviter de partir avec des données sensibles
- Utiliser un filtre sur l'écran
- Marquer l'équipement avec un signe distinctif

### Pendant la mission

- Garder les équipements sur sa personne, à défaut au moins les données.
- Protéger l'accès aux données et équipements par des mots de passe forts.
- Eviter de se séparer des équipements
- Utilisez un logiciel de chiffrement des données
- Pensez à effacer vos historiques de navigation et d'appels
- En cas d'interpellation ou de saisie de matériel par des autorités locales, prévenir l'entreprise.
- En cas de perte ou de vol contacter l'entreprise.
- Ne pas utiliser ou connecter les équipements que l'on vous offre (clé usb)
- Eviter de se connecter à des système informatiques quine sont pas de confiance.
- Ne pas se connecter aux bornes de rechargement USB

### Avant le retour de la mission

- Transferer toutes les données à l'entreprise de façon sécurisée
- Effacer les historiques d'appels et de navigation.

### Après la mission

- Changer les mots de passes utilisés pendant la mission
- Analyser les équipements (recherche d'infection)

#### Mesures techniques complémentaires

- Vérrouiller le BIOS pour éviter de modifier la configuration.
- Interdire le démarrage depuis d'autres supports que le DD principal.
- Vérrouiller l'accès à la séquence de démarrage.

## Mesure cryptographique

En cas de perte ou de vol de l'équipement, les données qu'il contient peuvent être exposées.
Il convient de chiffrer les supports de stockage.
Plusieurs méthodes sont possibles:

- Chiffrement de disque
- Chiffrement de partition
- Chiffrement de fichiers
- Lorsque le support de stockage est chiffré il va être nécéssaire de renseigner le secret de déchiffrement pour accéder aux données. (secret = clé secrète de chiffrement symétrique)

La clé secrète peut être renseignée de différente façon :

- sous la forme d'un mdp à saisir au lancement de la machine
- le clé peut être :
    - La clé de déchiffrement de données
    - la passphrase qui va déverrouiller la clé de chiffrement symétrique

Quid du stockage de la clé de déchiffrement ?
Elle peut être soit sur un composant matériel interne au poste : TPM Trusted Platform Manager
Soit sur un composant externe : clé USB, smartcard ...

Il convient de chiffrer le volume ou la partition sur lesquels sont stockées les données et ensuite chiffré les données les plus sensibles.
Les technologies disponibles pour le chiffrement de disques ou de partition :

- Bitlocker (windows)
- Luks
- VeraCrypt

cf [podcast nolimit secu veracrypt](https://www.nolimitsecu.fr/veracrypt/)

Pour le chiffrement de fichiers

- zed
- PGP/Gnupg
- OpenSSL

RGS : Qualification de produits
Différents niveau de qualifcation

- evaluation CSPN (Certification de sécurité de prmier niveau)
- critères commun EAL3+ et EAL4+ réalisé par des organismes accrédités CESTI (Centre d'évaluation de la sécurité des Technologies de l'information)

Pensez à la procédure de récupération en cas de perte de la clé. -> recopier la clé en lieu sur.

Les systèmes nomades évoluent dans un environnement sécurisé et ils doivent accéder à un environnement sécurisé.

## Mesures d'accès distants sécurisé au SI

- Mise en place de VPN
- Différents technologies
    - SSL/TLS
    - IPsec
    - ....
- Différents niveaux d'authentification
    - mots de passes
    - clés de chiffrement

## Mise en oeuvre d'une politique spécifique

- mise en oeuvre de paramètre renforcées dédiés à cet usage
- Homogéniser les paramètres (limiter la surface) : profils de configuration
- stratégie de restriction logicielle (applocker)
- Politique antivirus
- EMET (Enhanced Mitigation Experience Toolkit)

## Mise en place des mesures de support spécifiques

- Isolés du SI
- que faire en cas de défaillaince ou perte de l'équipement ?
- souscription de garanties spécifiques au niveau des assurances.

Les mesures prises doivent relever d'une analys du risque qui prends en compte les lieux depuis lesquels les équipements vaont être utilisés.

## Le cas particulier du télétravail

Dans iso 27002 paragraphe 11.7.2
Dans le cas du télétravail il convient de protéger le site de travail et de veiller à la mise en place des installations appropriées.

### Les risques du télétravail

- Le vol de matériel et d'informations
- Des enfants qui font de la merde
- Accès distant non autorisé du SI de l'entreprise
- Mauvais usage des équipements

Compte tenus de ces risque il va falloir prendre des mesures spécifiques

- Renforcer le niveau de protection physique du site
- nuissance de l'environnement
- utilisation d'un réseauu domestique non sur pour véhiculer des information sensibles

Problématique de nature juridique

- quid de la propriété des développements éffectués avec des équipements personnels
- Risque de complication en cas d'enquêtes