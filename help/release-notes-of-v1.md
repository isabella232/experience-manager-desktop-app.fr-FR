---
title: Notes de mise à jour de l’appli de bureau AEM version 1.x
description: Détails des mises à jour, améliorations, nouvelles fonctionnalités, compatibilité et liens de téléchargement pour l’appli de bureau AEM version 1.x.
uuid: b783c3f8-aa1e-4c05-b687-5894909769f5
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 3052549b-fe75-44fb-a55e-5cc612868f54
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f1ea381cc88b5382288b2479d26e976dc7289b88

---


# Notes de mise à jour de l’appli de bureau AEM v1.x{#aem-desktop-app-release-notes}

Pour la version 1.x de l’appli de bureau, voici les liens de téléchargement et les informations de compatibilité d’AEM.

| Produits | Appli de bureau Adobe Experience Manager (AEM) |
|---------------|--------------------------------------------------------------------|
| Version | 1.10 (1.10.0.6 sous Mac et 1.10.0.3 sous Windows) |
| Type | Version mineure |
| Date | 1.10.0.6 (Mac) : 15 avril 2020; 1.10.0.3 (Win) : 31 août 2018 |
| URL de téléchargement | [Mac OS X 64 bits](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-osx-1.10.0.6.dmg) ; [Windows 32 bits](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win32-1.10.0.3.exe) ; [Windows 64 bits](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win64-1.10.0.3.exe) |
| Compatibilité | AEM 6.5.x ; AEM 6.4.x ; AEM 6.3 SP2 ; AEM 6.2 SP1 CFP2+ ; AEM 6.1 SP2 CFP7+ |

>[!NOTE]
>
>La limite de taille de la mémoire cache n’est pas appliquée. Au démarrage de l’appli de bureau, la taille du cache est calculée une seule fois et une notification est affichée si elle est proche de la limite prédéfinie.

## Configuration requise et conditions préalables {#system-requirements-and-prerequisites}

L’appli de bureau AEM est compatible avec les systèmes d’exploitation suivants :

* Mac OS X 10.10 ou version ultérieure, avec les correctifs de bogues les plus récents.
* Windows 7 et Windows 10 avec les Service Packs et les correctifs de bogues les plus récents.

Adobe recommande vivement d’utiliser la version la plus récente de l’appli de bureau AEM pour bénéficier des dernières fonctionnalités, des correctifs de bogues les plus récents et d’un niveau de performance optimal.

La version de l’appli de bureau AEM que vous prévoyez d’installer sur votre ordinateur local nécessite une version spécifique du serveur AEM/des composants supplémentaires côté serveur (Service Packs, correctifs logiciels ou Feature Packs). Assurez-vous que le serveur AEM est configuré correctement avant de vous y connecter pour la première fois. Si vous avez besoin d’aide, contactez votre administrateur AEM.

Consultez le [tableau de compatibilité détaillé](#compatibilitymatrix) à la fin de ce document pour évaluer les conditions préalables à la configuration.

## Nouveautés de l’appli de bureau AEM 1.10 {#what-s-new-in-aem-desktop-app}

L’appli de bureau AEM 1.10 met l’accent sur l’amélioration de l’expérience utilisateur en ce qui concerne les chargements volumineux, les informations relatives aux opérations en arrière-plan et une expérience optimisée lors de l’ouverture de ressources avec des fichiers liés (comme InDesign).

>[!NOTE]
>
>Si vous utilisez macOS 10.15.4 ou version ultérieure, utilisez au moins la version 1.10.0.6 de l’application. Cette version de correctif est conforme aux exigences [de notation d’](https://developer.apple.com/news/?id=04102019a)Apple.

**Modification/extraction locale** : les chargements automatiques des modifications enregistrées dans les ressources peuvent être désactivés dans la fenêtre de statut. De cette façon, l’utilisateur peut continuer à traiter des fichiers et à enregistrer des modifications puis, lorsque tout est prêt, décider de transférer toutes les modifications.

**Fenêtre d’état des ressources simplifiée** : la fenêtre de statut a été simplifiée * L’onglet Uploads (Téléchargements) affiche désormais les différentes ressources, ainsi que les téléchargements de dossiers/massifs. L’ancien onglet Transferts en bloc a été supprimé.

**Icône d’application pour indiquer les transferts en bloc** : l’icône d’application affichera une incrustation « transfer » (transfert) pour indiquer qu’un téléchargement en masse est en cours.

**Notifications de conflits de mise à jour** : si l’application détecte un conflit en essayant de mettre à jour une ressource, elle affiche une notification, de sorte que l’utilisateur puisse examiner ce conflit sans avoir à surveiller la fenêtre de statut. Au démarrage, l’application recherche d’éventuels conflits, de sorte que l’utilisateur puisse les résoudre.

**Meilleur traitement des pertes de connexion** : les téléchargements en masse sont interrompus en cas de perte de connexion et l’utilisateur est en mesure de reprendre l’opération ultérieurement. Un bouton Retry (Réessayer) est disponible pour effectuer une nouvelle tentative en cas d’échec du téléchargement d’un fichier.

## Instructions d’installation {#installation-instructions}

Pour obtenir des instructions détaillées, voir [Installation et configuration de l’appli de bureau AEM](install-configure-app-v1.md).

## Améliorations effectuées dans les versions précédentes {#enhancements-in-the-previous-versions}

Cette version étend et remplace les versions précédentes de l’appli de bureau Experience Manager, qui fournissaient les améliorations principales suivantes :

* **Version 1.9/1.9.1** : reprise des téléchargements interrompus, fenêtre de statut améliorée, icônes indiquant le statut de l’application/de la connexion et récupération anticipée des ressources liées pour les fichiers InDesign
* **Version 1.8** : meilleur contrôle de la taille du cache pour l’utilisateur, expérience de connexion améliorée pour SAML/SSO sous Windows, prise en charge du proxy réseau .pac sous Mac et des problèmes signalés par les clients.
* **Version 1.7** : améliorations sur le plan de la stabilité et de la logique de mise en mémoire cache, meilleure prise en charge du proxy réseau et possibilité de nettoyer les fichiers internes après la désinstallation.
* **Version 1.6** : améliorations du processus de connexion pour différentes configurations de sécurité AEM, des performances et de la stabilité de l’application.
* **Version 1.5** : stabilité et résilience de l’application face aux différents problèmes de mise en réseau, amélioration de la capacité de prise en charge.
* **Version 1.4** : possibilité de charger des dossiers hiérarchiques en arrière-plan avec surveillance de la progression.
* **Version 1.3** : performances stables et améliorées lors de l’accès aux fichiers et de l’enregistrement des modifications dans AEM, en particulier à partir des applications de bureau Creative Cloud, telles que InDesign, Illustrator ou Photoshop. Cette version avait pour objectif d’offrir aux utilisateurs une expérience davantage similaire à celle d’un poste de travail local lorsqu’ils travaillaient avec des fichiers, tout en gérant simultanément les opérations de transfert de données réseau en arrière-plan.

### Améliorations disponibles depuis l’appli de bureau AEM 1.9 {#Enhancements-Available-Since-AEM-Desktop-App-19x}

L’appli de bureau Adobe Experience Manager (AEM) 1.9.1 était une version corrective qui corrigeait quelques problèmes majeurs rencontrés par les clients concernant l’extraction de ressources et la copie de fichiers d’un partage réseau vers un répertoire local.

* Les ressources extraites par un utilisateur ne doivent pas être accessibles à d’autres utilisateurs en vue de la modification (CQ-4246009)
* Prise en charge de la copie depuis un dossier mappé vers un dossier local lorsque le dossier utilisateur se trouve sur une partition de disque distincte (CQ-4243978)

L’appli de bureau AEM 1.9 mettait l’accent sur l’amélioration de l’expérience utilisateur en ce qui concerne les chargements volumineux, les informations relatives aux opérations en arrière-plan et une expérience optimisée lors de l’ouverture de ressources avec des fichiers liés (comme InDesign).

**Chargements pouvant reprendre**
Une option disponible dans la nouvelle fenêtre Asset Status (Statut de la ressource) permet de suspendre/relancer les chargements dans le cas de fichiers volumineux.
**Amélioration de la fenêtre Asset Status (Statut de la ressource)**
Une fenêtre de statut des ressources améliorée fournit des informations sur les ressources dans les cas suivants :
Modifications

* Affiche les modifications placées actuellement en file d’attente.
* Affiche les transferts en cours, y compris une barre de progression, la vitesse de transfert, la taille totale du fichier et la taille transférée jusqu’à présent.
* Transferts terminés affichés avec la taille totale transférée et le débit final.
* Les transferts ayant échoué sont accompagnés d’un message d’erreur et d’informations de transfert, le cas échéant.
* Les transferts ayant échoué à trois reprises affichent un message d’erreur.
* Les fichiers en conflit sont affichés avec une icône sur laquelle l’utilisateur peut cliquer. S’il clique sur cette icône, une boîte de dialogue s’ouvre avec une explication, et deux options lui sont proposées :
   * « Keep Mine » (Conserver mon fichier) : transfère immédiatement le fichier sur le serveur.
   * « Overwrite Mine » (Remplacer mon fichier) : supprime immédiatement le fichier local et télécharge une nouvelle copie à partir du serveur.

Téléchargements

* Affiche les téléchargements en cours, y compris la vitesse de transfert et la taille transférée jusqu’à présent.
* Téléchargements terminés affichés avec le volume transféré final, le débit final et une icône qui ouvre le fichier lorsque l’utilisateur clique sur celle-ci (disponible uniquement pour les fichiers uniques).
* Les téléchargements ayant échoué sont accompagnés d’un message d’erreur et d’informations sur le transfert, le cas échéant.
* Le pied de page affiche le nombre total de fichiers téléchargés, ainsi que la vitesse de transfert moyenne..
* Si un utilisateur choisit d’ouvrir ou de modifier plusieurs fichiers à partir de l’interface utilisateur web AEM Assets, ceux-ci sont regroupés et affichés (par exemple, sous la forme « myasset.jpeg and 4 more file(s) » (myasset.jpeg et 4 autres fichiers)).
* Lorsque vous téléchargez des documents InDesign comprenant des ressources liées stockées dans AEM Assets, l’application télécharge l’ensemble des ressources liées avant d’ouvrir le document InDesign et d’indiquer le téléchargement des ressources liées sous la forme (5 sur 24), par exemple.

Bulk Uploads (Téléchargements en masse) : cette boîte de dialogue s’affiche lorsque vous chargez des hiérarchies de dossiers de grande taille par le biais de l’option Create > Upload Folder (Créer > Transférer un dossier) dans l’interface utilisateur web AEM ou lorsque vous copiez et sélectionnez Paste Assets (Coller des ressources) dans le Finder ou l’Explorateur dans le menu contextuel de l’appli de bureau.

* Affiche les transferts en cours, y compris une barre de progression et le nom du fichier en cours de transfert.
* Les transferts en cours s’accompagnent d’une icône qui annule l’opération lorsque l’utilisateur clique sur celle-ci. Le transfert s’arrête une fois le transfert du fichier en cours terminé.
* Les processus de transfert qui ont échoué sont affichés, accompagnés d’un message d’erreur (uniquement si tout le transfert échoue).
* Si le transfert d’un seul fichier échoue, il est affiché sur l’onglet sous la forme d’une erreur. Dans le cas contraire, les fichiers individuels ne sont pas affichés sur l’onglet ; une seule entrée est répertoriée pour l’ensemble du téléchargement.

**Icônes indiquant le statut des opérations en arrière-plan**
L’icône de l’application indique le statut des opérations en arrière-plan afin de fournir un meilleur indice visuel aux utilisateurs. Par exemple, lorsque l’application n’est pas connectée à AEM, l’icône est grisée. Lorsqu’un téléchargement est actif, une incrustation « sync » est affichée, etc.

**Pré-récupération des ressources liées**
Pour améliorer l’expérience utilisateur lors de l’utilisation de documents InDesign contenant des ressources liées stockées dans AEM, l’appli de bureau tente d’effectuer une pré-récupération de ces fichiers liés dans le cache local avant de télécharger et d’ouvrir le document InDesign. L’utilisateur dispose ainsi des fichiers liés en local et ne doit pas attendre longtemps pour y accéder dans InDesign (dans le panneau Links (Liens)).
Veuillez noter que la pré-récupération ne fonctionne que si AEM reconnaît les liens du côté serveur. Dans le cas d’une ressource contenant des liens reconnus, une liste de « Références » figure dans la vue Propriétés de la ressource InDesign.

### Améliorations disponibles depuis l’appli de bureau AEM 1.8.x{#enhancements-available-since-aem-desktop-app-18x}

L’appli de bureau AEM 1.8.1 s’accompagnait d’améliorations au niveau de l’ouverture simultanée de plusieurs fichiers à partir de l’interface utilisateur AEM vers la version 1.8 (CQ-4237747, CQ-4238780). Les améliorations apportées dans l’appli de bureau AEM 1.8 sont les suivantes :

* Mise en cache : nouvelle interface utilisateur pour gérer le cache de l’appli de bureau AEM (CQ-4208690), incluant les fonctionnalités suivantes :
   * Affichage de la taille actuelle du cache
   * Définition de la taille maximale du cache avant l’envoi d’une notification
   * La taille du cache est vérifiée uniquement au démarrage de l’appli de bureau, et une notification est envoyée si cette taille atteint la limite configurée
   * La nouvelle interface utilisateur contient désormais un bouton d’effacement du cache
* Connexion : (Windows) connexion fixe à une instance AEM configurée pour utiliser SAML et SSL (CQ-4216353)
* Réseau :
   * lors de l’expiration d’une session AEM, l’utilisateur en est maintenant informé et peut cliquer sur la notification pour se reconnecter (CQ-4202028)
   * (Mac) Ajout d’une prise en charge pour se connecter à AEM à l’aide d’une configuration de proxy .pac (CQ-4233430)
   * (Windows) Résolution de problèmes relatifs à la boîte de dialogue Advanced > Login URL (Avancé > URL de connexion) (CQ-4236061)
* Correctifs :
   * Boîte de dialogue More Asset Info (Plus d’informations sur la ressource) : dans certains cas, la barre d’actions n’était pas visible (CQ-4208540)
   * (Windows) Le fichier peut maintenant être synchronisé après rétablissement d’une version antérieure à partir de l’interface utilisateur AEM Assets (CQ-4216411)

### Améliorations disponibles depuis l’appli de bureau AEM 1.7{#Enhancements-Available-Since-AEM-Desktop-App-17}

* Stabilité :
   * stabilité améliorée lorsque l’appli de bureau AEM se connecte à un serveur AEM surchargé (CQ-4224803)
   * Stabilité améliorée lorsque de nombreux fichiers sont demandés (CQ-4224212)
   * Mise à jour des ressources améliorée avec vérification supplémentaire (CQ-4228291)
* Mise en cache :
   * Résolution des erreurs de disque et des problèmes d’ouverture de fichiers dans Photoshop, InDesign, Finder (CQ-4223993, CQ-4217603, CQ-4223717)
   * Mise en cache améliorée pour éviter les binaires de taille nulle (CQ-4216599)
* Connexion: autorisation de connexion avec l’option strictSSL désactivée pour les configurations spéciales (comme les certificats délivrés en local) (CQ-4223949)
* Mise en réseau : prise en charge améliorée pour une connexion sur un serveur proxy de réseau (CQ-4223477, CQ-4221280, CQ-4206854)
* Installation et désinstallation :
   * (Windows) Désinstallation de Cleaner (CQ-4220906)
   * [Windows 32 bits] Échec du programme d’installation lors de la tentative d’installation de Microsoft .NET Framework v.4.5 (CQ-4218084)
   * (Mac) Script manuel pour la suppression complète des fichiers de l’appli de bureau (CQ-4216489)

>[!NOTE]
>
>Problèmes détectés dans les chargements de l’appli de bureau AEM 1.7 bêta (les problèmes qui ne figuraient pas dans la version 1.6 ne sont pas repris dans les notes de mise à jour).

### Améliorations disponibles depuis l’appli de bureau AEM 1.6{#Enhancements-Available-Since-AEM-Desktop-App-16}

* Documentation : nouvelles [Bonnes pratiques pour la documentation de l’application v1.x](https://helpx.adobe.com/fr/experience-manager/6-3/assets/using/aem-desktop-app-best-practices.html)
* Amélioration du processus de connexion à AEM :
   * Amélioration de la prise en charge du format SAML * - assouplissement des règles (CQ-4202781).
   * Ajout de la possibilité de configurer une URL de connexion distincte dans les préférences (CQ-4214052, CQ-4214051).
* Convivialité : notification de l’utilisateur lorsqu’une ressource est toujours en cours de téléchargement pour les ressources volumineuses (CQ-4216284)
* Mise en réseau :
   * Mise en cache DNS (CQ-4210176)
   * Prise en charge de la connexion via un proxy sous Windows (CQ-4206854)
* Mise en cache et accès au partage de réseau dans le Finder/l’Explorateur :
   * Icône de verrouillage désormais visible pour les ressources extraites sous Windows 10 (CQ-90957).
   * Le contenu du dossier peut disparaître/réapparaître dans le partage réseau (CQ-4209160, CQ-4210180).
   * Erreur lors du chargement d’un fichier, en raison d’un conflit signalé dans le statut de la file d’attente des chargements (CQ-4215727).
   * Lors de l’ouverture de plusieurs fichiers à partir du dossier de l’appli de bureau dans PS, des fichiers tronqués ou des messages incomplets peuvent s’afficher (CQ-4216276).
* Correctifs en matière de stabilité et de performances :
   * Amélioration des performances lors de la navigation dans des dossiers comportant de nombreuses ressources (CQ-4214933).
   * L’appli de bureau version 1.5 peut ralentir l’ordinateur de bureau au fil du temps (CQ-4209159).
   * L’affichage du statut de la file d’attente fonctionne uniquement pour l’utilisateur qui a installé l’application (CQ-4212199).
   * (Windows) Assurez-vous que le programme d’installation 32 bits ne contient pas de code 64 bits (CQ-4217406).
* Problèmes sélectionnés identifiés et résolus dans la version bêta 1.6 :
   * Utilisation intensive du processeur (CQ-4218070).
   * Faire glisser et déposer des fichiers génère une erreur lors du chargement vers AEM (CQ-4217006).

### Améliorations disponibles depuis l’appli de bureau AEM 1.5{#Enhancements-Available-Since-AEM-Desktop-App-15}

**Version 1.5.1.5 pour Mac OS X :** La version 1.5.1.5 offre les avantages suivants :

* Nouvelles fonctionnalités et améliorations : ajout de la fonctionnalité Copier/coller à l’intégration du Finder pour permettre le transfert direct à partir du bureau vers AEM (CQ-4208158)
* Corrections de bogues :
   * Correction d’un problème d’erreur 43 qui se produisait parfois lors du changement de nom d’une ressource (CQ-4207900)
   * La restauration d’une ancienne version depuis la chronologie dans AEM ne met pas à jour la ressource dans le Finder (CQ-4205194)
   * L’appli de bureau se bloque lors de la navigation dans des répertoires imbriqués volumineux (CQ-4208539)
   * Le point de montage de l’appli de bureau est désormais /Volumes/DAM, et est donc cohérent pour tous les utilisateurs (CQ-4208159)
   * Le placement d’un fichier dans InDesign pour la première fois déclenche un avertissement de mise à jour (CQ-4207454)

Remarque concernant les avertissements relatifs aux liens : les applications Creative Cloud (par exemple, InDesign) prennent un « instantané » de la date et de l’heure de la dernière modification de l’élément au moment où il est placé. Si cette date et cette heure changent ultérieurement, l’application Adobe Creative Cloud signale que les liens sont obsolètes. Ce signalement revêt plusieurs formes :

* À son lancement, l’application Adobe Creative Cloud affiche une boîte de dialogue informant l’utilisateur que les ressources liées sont obsolètes et invite l’utilisateur à prendre des mesures.
* Si l’application Adobe Creative Cloud est déjà en cours d’exécution, une icône d’avertissement en forme de triangle jaune apparaît sur la ressource liée.

Ce comportement est identique pour les ressources du disque local et celles du répertoire monté de l’appli de bureau AEM, avec les exceptions suivantes :

* Si une ressource importée est modifiée par un autre utilisateur, l’icône d’avertissement s’affiche la première fois que l’autre utilisateur ouvre un document contenant cette ressource. Cela se produira uniquement si la ressource importée a déjà été mise en cache localement..
* Si un utilisateur modifie une ressource importée par l’intermédiaire du répertoire monté de l’appli de bureau AEM, puis efface le cache local, la ressource est signalée comme obsolète.

Ces deux cas sont attendus et sont des répercussions secondaires de l’architecture « synchronisation différée » de l’appli de bureau AEM.

**Version 1.5.0.x pour Mac OS X et Windows** : cette version de l’appli de bureau AEM offre les avantages suivants :

* Amélioration de la stabilité et de la résilience face aux problèmes de réseau
   * Mappage plus stable des dossiers AEM Assets (CQ-103276, CQ-4204669, CQ-4203957)
   * Amélioration de la gestion des fichiers en mémoire cache (CQ-4204336, CQ-4206263)
   * Amélioration de la gestion du téléchargement/chargement de fichiers volumineux de plus de 2 Go (CQ-4206438)
   * Correction d’une « Erreur 36 » lors du déplacement ou du changement de nom d’un plus grand nombre de fichiers dans le Finder (CQ-4204640)
* Optimisations de la communication réseau avec le serveur AEM (CQ-4204974, CQ-100903)
* Plus grande fiabilité de l’ouverture, du placement et de l’enregistrement des ressources AEM dans les applications Creative Cloud (CQ-4203968, CQ-4205511, CQ-103543, CQ-4207141, CQ-90980)
* Amélioration de la capacité de prise en charge : option pour effacer le cache (CQ-4202541), accès facile aux journaux (CQ-4202340, CQ-4204673)
* Autres correctifs :
   * Amélioration de la prise en charge des ressources et des dossiers comportant des caractères japonais dans les paramètres de nom/langue autres que l’anglais (CQ-4195433, CQ-4205793, CQ-4199446)
   * Amélioration de la gestion de la connexion avec SSL (CQ-4200217)
   * Amélioration de la fiabilité du montage de partage (CQ-4200793)
   * Diverses améliorations de la stabilité (CQ-4207539, CQ-4200378)
   * Amélioration de la gestion de l’URL d’AEM Assets dans les préférences (CQ-97388)

### Améliorations disponibles depuis l’appli de bureau AEM 1.4{#Enhancements-Available-Since-AEM-Desktop-App-14}

* Simplification du chargement des dossiers hiérarchiques par l’intermédiaire de la nouvelle opération Create > Upload Folder (Créer > Charger le dossier) de l’interface utilisateur tactile
   * L’action lance un chargement de dossier effectué par l’appli de bureau
   * L’appli de bureau traverse la hiérarchie de dossiers donnée sur le bureau en arrière-plan et charge les fichiers dans AEM Assets.
   * L’utilisateur peut surveiller la progression dans la nouvelle fenêtre d’état de la file d’attente des chargements à l’aide d’une barre de progression pour les opérations en cours.
   * Le statut de la file d’attente des chargements fournit également des informations de résolution de problème (par exemple, aucune connexion au serveur)
* Nouvelle opération de modification dans l’interface utilisateur tactile, qui combine les opérations d’extraction et d’ouverture
* Optimisation du regroupement des opérations liées au bureau dans l’interface utilisateur tactile (AEM 6.3)
* Amélioration de la compatibilité avec les dernières versions du système d’exploitation
* Correctifs signalés par le client

### Améliorations disponibles depuis l’appli de bureau AEM 1.3{#Enhancements-Available-Since-AEM-Desktop-App-13}

* Gains d’efficacité. Les utilisateurs passent moins de temps à attendre que les opérations réseau se terminent.
* Amélioration de l’intégration du Finder, qui offre une amélioration de la stabilité et un accès aux fonctionnalités telles que les miniatures
* Améliorations de la mise en cache et des performances
* Amélioration de la prise en charge de l’enregistrement directement depuis les applications de bureau (PS, ID, AI, etc.)
* Amélioration de l’intégration avec Mac OS (le protocole du lecteur réseau local est passé de WebDAV à SMB1, plus stable).
* L’appli de bureau se connecte au serveur AEM à l’aide du protocole HTTP RESTful natif d’AEM.
* Les fichiers sont d’abord enregistrés localement puis transférés vers AEM en arrière-plan après une période prédéfinie (30 secondes). Cela réduit le temps d’enregistrement des fichiers.
* Amélioration de la gestion des applications de bureau qui utilisent des opérations de fichiers intermédiaires pour enregistrer un fichier (enregistrements partiels et fichiers temporaires), ce qui permet à la chronologie d’AEM Assets d’afficher les informations correctes de version et de chargement des ressources.
* Boîte de dialogue fournie pour effectuer le suivi de l’état des tâches de chargement en arrière-plan.

## Liste des modifications     {#list-of-changes}

### Point de montage sous Mac {#mount-point-on-mac}

Depuis MacOS 10.12 (Sierra), Apple a modifié les autorisations, de manière plus restrictive, pour le dossier /Volumes utilisé pour monter les lecteurs et périphériques réseau. La création d’un point de montage requiert désormais des droits d’administration. Ce problème a été résolu dans la version 10.12.5 de MacOS.

Comme l’appli de bureau AEM doit fonctionner pour les utilisateurs ne disposant pas de droits d’administration pour l’ordinateur local, le point de montage du référentiel AEM Assets a été remplacé dans les versions 1.4 et 1.5 par un sous-dossier DAM du dossier local de l’utilisateur sous MacOS (CQ-104183).

Comme le dossier /Volumes ne nécessite plus de droits d’administration, cette modification a été annulée dans la version 1.5.1. Cela permet également aux utilisateurs de MacOS de partager des documents InDesign disposant de ressources AEM importées.

### Modification de protocoles (depuis la version 1.3) {#protocol-change-since}

* Mac OS X :
   * Le protocole du lecteur réseau local pour l’intégration de bureau OS X a été remplacé par SMB1, à la place de WebDAV.
   * Le référentiel AEM monté avec l’appli de bureau sera visible sous la forme d’un lecteur réseau « smb » dans le Finder, au lieu d’un lecteur WebDAV.
* Windows :
   * Le protocole de lecteur réseau local pour les intégrations de bureau Windows reste le même ; AEM est monté en tant que partage WebDAV.
* Pour les deux plateformes (Windows et Mac) :
   * Le protocole permettant d’accéder/de télécharger des ressources et de charger des modifications dans AEM a été remplacé par le protocole natif d’AEM, qui est un protocole RESTful basé sur HTTP. Il offre un meilleur contrôle sur les opérations réseau et sa compatibilité avec l’infrastructure réseau est meilleure.

>[!NOTE]
>
>Sous Mac OS X, le passage du protocole de lecteur réseau local de WebDAV à SMB1 résulte en un chemin d’accès local différent vers la même ressource du référentiel. Cela peut avoir un impact sur les liens vers les fichiers placés dans les applications Adobe Creative Cloud via la commande « Place » (Placer). Pour plus d’informations, reportez-vous à [Utilisation de l’appli de bureau AEM](use-app-v1.md).

### Gestion des fichiers (depuis la version 1.3) {#file-handling-since}

* Les fichiers sont automatiquement mis à jour après une période prédéfinie (actuellement, 30 s).
* Les fichiers extraits par d’autres utilisateurs sont marqués comme étant en lecture seule.
* Les fichiers sont enregistrés en deux phases dans un emplacement de lecteur réseau monté par l’intermédiaire de l’appli de bureau.
* Au cours de la première phase, un fichier est enregistré en local. Ainsi, l’utilisateur qui enregistre le fichier n’a pas besoin d’attendre que le fichier soit entièrement transféré vers AEM, et peut reprendre le travail dès que le fichier est enregistré.
* Dans la seconde phase, l’appli de bureau charge le fichier mis à jour vers le serveur AEM après une période prédéfinie (par exemple, 30 s). Cette opération s’effectue en arrière-plan. Utilisez l’option **Show Background File Sync Status** (Afficher le statut de synchronisation du fichier en arrière-plan) pour afficher le statut de l’opération de chargement.

## Remarques importantes {#important-notices}

**Chargement des dossiers.** Il est recommandé d’utiliser la nouvelle fonctionnalité de chargement de dossiers pour charger des dossiers hiérarchiques plus volumineux dans AEM plutôt que d’utiliser la fonction de copie/glisser-déposer dans un référentiel AEM monté à partir du Finder/de l’Explorateur. Lors de l’utilisation de la fonctionnalité de chargement de dossiers, l’appli de bureau communique directement avec AEM et dispose ainsi d’un meilleur contrôle sur l’ensemble du processus.

**Maintenir la session AEM disponible.** L’appli de bureau AEM dépend d’une session ouverte sur le serveur AEM Assets pour garantir son bon fonctionnement. Il est recommandé aux utilisateurs travaillant quotidiennement avec l’appli de bureau de démonter AEM Assets à la fin de leur journée pour forcer la déconnexion, puis de « monter AEM Assets » le matin pour s’assurer qu’ils sont connectés et que le partage réseau est opérationnel.

**Désactiver l’option « Aperçu de l’icône » dans le Finder.** Pour une navigation performante avec le Finder dans les dossiers volumineux, en particulier avec une mauvaise connectivité réseau, assurez-vous que les options « Icônes » et « Aperçu de l’icône » sont désactivées. Sinon, le Finder commence à télécharger chaque ressource dans un dossier afin de générer un petit aperçu, ce qui peut entraîner des performances médiocres et une utilisation élevée de la bande passante (CQ-4219779).

* Dans le Finder, accédez au dossier réseau partagé d’AEM Assets
* Cliquez avec le bouton droit de la souris sur le point de montage DAM
* Sélectionnez les options Afficher la vue
* Désactivez la case « Afficher l’aperçu de l’icône »
* Cliquez sur « Utiliser comme valeurs par défaut »

**Nettoyer le cache lors de la connexion à un nouveau serveur AEM.** Si l’appli de bureau se connecte à un autre serveur AEM doté de la même URL, le cache n’est pas effacé automatiquement. Effacez le cache manuellement pour garantir des opérations correctes. Notez que cela se produit généralement lors de tests, lorsque les installations AEM peuvent être remplacées en cours d’exécution sur la même URL (CQ-4216982).

**Utiliser des certificats SSL signés par une autorité de certification.** Veuillez noter que l’appli de bureau AEM ne prend pas en charge les certificats SSL auto-signés lors de la connexion à AEM via une connexion sécurisée HTTPS. Un certificat signé par une autorité de certification est requis sur le serveur pour ce type de connexion. (CQ-87941)

## Problèmes connus {#known-issues}

* Général :
   * Les URL du serveur sont requises pour pointer vers le serveur sans chemin d’accès (par exemple, `http://server`, `https://server`, `http://server:port` ou `https://server:port`). Les chemins d’accès au contexte et les sous-dossiers de contexte autres que /content/dam ne sont pas pris en charge (CQ-89343, CQ-87272).
* Noms de fichiers/localisation :
   * Les noms de fichiers et de dossiers comportant des caractères réservés ne sont pas gérés correctement. Veillez à utiliser les noms de fichiers et de dossiers qui correspondent aux exigences d’AEM (CQ-93361, CQ-93308, CQ-89276, CQ-4217183).
   * Certaines applications telles que Adobe Illustrator peuvent créer des fichiers dont les noms ne sont pas pris en charge dans AEM. Par exemple, ajouter `Converted` après la conversion d’un fichier empêche son chargement (CQ-4216985).
   * Les ressources avec des noms internationaux peuvent apparaître et disparaître toutes les quelques secondes.
* Archivage et extraction :
   * Une ressource extraite par un utilisateur ne peut pas être ouverte pour un autre utilisateur, que ce soit par l’option Open (Ouvrir) de l’interface utilisateur tactile ou directement sur le bureau. Certaines applications peuvent la signaler comme verrouillée, mais aussi corrompue ou même bloquée lors d’une tentative d’ouverture. (CQ-4199234)
   * La modification simultanée de fichiers par plusieurs utilisateurs peut entraîner la perte de certaines modifications. La solution consiste à utiliser la fonctionnalité        D’archivage/d’extraction pour empêcher plusieurs utilisateurs de modifier le même fichier (CQ-97035).
   * Certaines applications ne prennent pas en charge correctement l’indicateur de lecture seule, ce qui permet à un utilisateur d’enregistrer un fichier extrait par un autre utilisateur. Le fichier modifié n’est pas transféré tant que l’autre utilisateur n’a pas archivé le fichier. Les deux modifications sont disponibles dans AEM sous la forme de versions différentes de la ressource (CQ-89551, CQ-87572, CQ-89615).
   * Les états « extrait » et « en lecture seule » sont signalés indépendamment dans le Finder. Cela entraîne l’affichage de 2 icônes de verrouillage lorsqu’un utilisateur extrait une ressource (CQ-89507).
* Intégration du Finder :
   * Lorsque vous effectuer un glisser/déplacer de fichiers volumineux, le Finder peut expirer pendant le transfert des fichiers en arrière-plan. Cela provoque une `Error - 36` La solution consiste à glisser la ressource ou à l’ouvrir à nouveau (CQ-4219628).
   * Le rechargement manuel du dossier ne fonctionne pas toujours. Solution : patientez 30 secondes pour que le dossier soit automatiquement mis à jour. (CQ-97389)
   * L’option More Asset Info... (Plus d’informations sur la ressource...) est limitée aux sélections de fichiers uniques (CQ-89542, CQ-87656).
   * L’option Ouvrir dans AEM Assets… est limitée à la sélection de fichiers et de dossiers uniques (CQ-83382).
   * Erreur lors du changement de nom des ressources sans extension (CQ-4218971).
* Fonctionnalité Copier/coller : la fonctionnalité Coller est disponible lorsqu’aucune ressource n’a été copiée dans le Presse-papiers.
* Windows :
   * Les fichiers avec des flux de données alternatifs (ADS, Alternate Data Streams) ne sont entièrement pris en charge que par NTFS. Si vous copiez ces fichiers sur le partage WebDAV fourni par l’appli de bureau, une boîte de dialogue d’avertissement indique à l’utilisateur que le fichier contient des propriétés ne pouvant pas être copiées vers le nouvel emplacement. Cela ne pose généralement pas problème puisque les propriétés ne sont pertinentes que pour une application spécifique du bureau de l’utilisateur et n’ont rien à voir avec le contenu réel du fichier (CQ-103770) (Windows).
   * L’appli de bureau sous Windows doit être installée par l’utilisateur qui l’utilise (CQ-4216389) (Windows).
   * L’appli peut se bloquer, dans certains cas, lorsque vous cliquez sur le bouton Retry (Réessayer) pour un transfert qui a échoué ; après avoir relancé un transfert par lots alors qu’aucune connexion n’est établie, par exemple (CQ-4251884) (Windows).

## Ressources utiles {#helpful-resources}

* [Documentation AEM](https://helpx.adobe.com/fr/support/experience-manager/6-4.html)
* [Utilisation de l’appli de bureau AEM v1.x](use-app-v1.md)
* [Bonnes pratiques relatives à l’appli de bureau v1.x](best-practices-for-v1.md)

## Tableau de compatibilité et conditions préalables {#compatibilitymatrix}

L’appli de bureau AEM fonctionne avec différentes versions d’AEM. Voir le tableau de compatibilité pour connaître les versions prises en charge.

| Version | Révision | Date de publication | Compatibilité |
|---------|------------------------|--------------|-------------------------------------------------------------|
| 1.10 | 1.10.0.3 (Mac et Windows) | 31 août 2018 | AEM 6.5 ; AEM 6.4 SP1 ; AEM 6.3 SP2 ; AEM 6.2 SP1 CFP2+ ; AEM 6.1 SP2 CFP7+ |
| 1.9 | 1.9.1.1 (Mac et Windows) | 21 juin 2018 | AEM 6.4 ; AEM 6.3 SP1 ; AEM 6.2 SP1 CFP2+ ; AEM 6.1 SP2 CFP7+ |
| 1.8 | 1.8.1.0 (Mac et Windows) | 28 mars 2018 | AEM 6.4 ; AEM 6.3 SP1 ; AEM 6.2 SP1 CFP2+ ; AEM 6.1 SP2 CFP7+ |
| 1.7 | 1.7.0.3 (Mac et Windows) | Jan 10, 2018 |  AEM 6.3 SP1 ; AEM 6.2 SP1 CFP2+ ; AEM 6.1 SP2 CFP7+ |
