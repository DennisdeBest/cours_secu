# TP3

## Chiffrement des données

- Vos postes de travail Windows 10 font partie d'un domaine Active Directory géré par un contrôleur de domaine Windows server 2012.
- Vous devrez donc utiliser les technologies Microsoft Bitlocker1 pour gérer le chiffrement des volumes de ces postes, en prenant en compte les contraintes suivantes :
    - Vous devrez mettre en oeuvre le chiffrement intégral des disques,
    - Vous devrez utiliser le chiffrement avec la prise en charge d'un TPM. Vous expliquerez alors ce qu'est un TPM, et quels sont les modes de déploiement possibles.
    - Vous mettrez ensuite en oeuvre le chiffrement avec utilisation du TPM avec code confidentiel.
    - Pour chacune des manipulations vous étudierez la possibilité d'utiliser la ligne de commande.

## Intégration à Active Directory et procédure de récupération des disques chiffrés :

- Vous étudierez les fonctionnalités Bitlocker intégrées à Active Directory, et mettrez en oeuvre une stratégie de groupe pour déployer Bitlocker.
- Vous mettrez en oeuvre la procédure nécessaire à la récupération des volumes chiffrés. Vous expliquerez le fonctionnement de la visionneuse des mots de passe de récupération BitLocker, et utiliserez ces fonctionnalités pour tester et appliquer votre procédure de récupération.

## Mise en oeuvre des accès distant

- Votre client utilise Active Directory sur son réseau, et dispose déjà d'une infrastructure à clef publique Microsoft. Les technologies employées sur le domaine sont celles de Windows Server 2012R2.
- Vous devrez donc tenir compte de cela pour choisir votre solution VPN. Le client souhaite également avoir une solution d'accès distant basée sur IPSEC, disposant d'une authentification des utilisateurs par certificat + mot de passe.