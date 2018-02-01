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
### Plan

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
<table><tr><td>2</td><td>3</td><td>4</td></tr></table>
<table><tr><td>3</td><td>4</td><td>5</td></tr></table>
<table><tr><td>4</td><td>5</td><td>6</td></tr></table>
<table><tr><td>5</td><td>6</td><td>7</td></tr></table>
<table><tr><td>6</td><td>7</td><td>8</td></tr></table>
<table><tr><td>7</td><td>8</td><td>9</td></tr></table>
<table><tr><td>8</td><td>9</td><td>10</td></tr></table>
</td>
<td>
<table><tr><td>3</td><td>4</td><td>5</td></tr></table>
<table><tr><td>4</td><td>5</td><td>6</td></tr></table>
<table><tr><td>5</td><td>6</td><td>7</td></tr></table>
<table><tr><td>6</td><td>7</td><td>8</td></tr></table>
<table><tr><td>7</td><td>8</td><td>9</td></tr></table>
<table><tr><td>8</td><td>9</td><td>10</td></tr></table>
<table><tr><td>9</td><td>10</td><td>11</td></tr></table>
</td>
<td>
<table><tr><td>4</td><td>5</td><td>6</td></tr></table>
<table><tr><td>5</td><td>6</td><td>7</td></tr></table>
<table><tr><td>6</td><td>7</td><td>8</td></tr></table>
<table><tr><td>7</td><td>8</td><td>9</td></tr></table>
<table><tr><td>8</td><td>9</td><td>10</td></tr></table>
<table><tr><td>9</td><td>10</td><td>11</td></tr></table>
<table><tr><td>10</td><td>11</td><td>12</td></tr></table>
</td>
</table>