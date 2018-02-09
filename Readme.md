# Sécurité des SI



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

