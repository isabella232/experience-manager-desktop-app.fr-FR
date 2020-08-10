---
title: Notes de mise à jour de l’appli de bureau Adobe Experience Manager
description: Détails des mises à jour, améliorations, nouvelles fonctionnalités, compatibilité et liens de téléchargement pour l’appli de bureau Adobe Experience Manager.
uuid: b783c3f8-aa1e-4c05-b687-5894909769f5
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 3052549b-fe75-44fb-a55e-5cc612868f54
index: y
internal: n
snippet: y
mini-toc-levels: 1
translation-type: ht
source-git-commit: 3eb9ab89ff6338fb29cfad1a031944119908d0a2
workflow-type: ht
source-wordcount: '1320'
ht-degree: 100%

---


# Notes de mise à jour de l’appli de bureau Adobe Experience Manager {#release-notes-v2}

| Produits | Appli de bureau Adobe Experience Manager |
|--- |--- |
| Version de l’application (révision) | 2.0 (2.0.2.0) |
| Versions d’AEM prises en charge | AEM as a Cloud Service ; AEM 6.5 ; AEM 6.4 ; AEM 6.3 (avec package de compatibilité) |
| Type | Version mineure |
| Date de publication | 15 avril 2020 (Mac et Windows) |
| URL de téléchargement | [macOS 64 bits](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-osx-2.0.2.0.dmg) ; [Windows 64 bits](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win64-2.0.2.0.exe) ; [Windows 32 bits](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win32-2.0.2.0.exe) |

## Configuration requise et conditions préalables {#system-requirements-and-prerequisites-v2}

L’appli de bureau Adobe Experience Manager est compatible avec les systèmes d’exploitation suivants :

* Mac OS X 10.14 ou version ultérieure, avec les correctifs de bogues les plus récents.

* Windows 7 et Windows 10 avec les Service Packs et les correctifs de bogues les plus récents.

L’application fonctionne avec les versions d’Experience Manager suivantes, qu’elles soient déployées en tant que Cloud Service, sur Adobe Managed Services (AMS) ou On-Premise :

* [Experience Manager as a Cloud Service](https://docs.adobe.com/content/help/fr-FR/experience-manager-cloud-service/release-notes/home.html).

* [Experience Manager 6.5.0](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/release-notes/release-notes.html) ou version plus récente.

* [Experience Manager 6.4.4](https://docs.adobe.com/content/help/fr-FR/experience-manager-64/release-notes/release-notes.html) ou version plus récente.

* Experience Manager 6.4.0–6.4.3 avec [package de compatibilité](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support).

>[!NOTE]
>
>La prise en charge de l’appli de bureau pour Experience Manager 6.3 est obsolète. Adobe recommande la mise à niveau vers une version plus récente et prise en charge d’Adobe Experience Manager.
>Experience Manager 6.3.3.1 ou version ultérieure fonctionne avec l’appli de bureau après l’installation du [package de compatibilité](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support). Aucun package de ce type n’est disponible pour Experience Manager 6.3, car aucun [Service Pack n’est planifié](https://helpx.adobe.com/fr/experience-manager/maintenance-releases-roadmap.html).

La version que vous prévoyez d’installer sur votre ordinateur local nécessite une version spécifique du serveur Adobe Experience Manager/des composants supplémentaires côté serveur (Service Packs, correctifs logiciels ou Feature Packs). Contactez votre administrateur Adobe Experience Manager pour obtenir de l’aide.

### Prise en charge de différents types de ressources et de fichiers {#support-for-file-types}

L’application prend en charge les ressources stockées dans Adobe Experience Manager qui représentent un fichier binaire pour ses opérations de base. L’ouverture de fichiers dans l’application de bureau native dépend de l’association du système d’exploitation des types de fichiers spécifiques (par exemple, PNG ou JPG) à des applications spécifiques (par exemple, Mac Preview ou Adobe Photoshop).

Certains types de fichiers prennent en charge le placement de ressources liées dans le fichier binaire. L’application pré-télécharge les ressources liées si la ressource est présente dans le référentiel Experience Manager lorsque ces fichiers binaires sont ouverts à l’aide de l’appli de bureau. Les types de fichiers actuellement pris en charge sont les suivants :

* Fichiers [!DNL Adobe InDesign] (format INDD)
* Fichiers [!DNL Adobe Illustrator] (format AI)
* Fichiers [!DNL Adobe Photoshop] (format PS)

Cette fonctionnalité est prise en charge avec Adobe Creative Cloud 2018 et les versions Creative Cloud 2019 de l’application ci-dessus. L’application utilise une approche heuristique et de la meilleure correspondance pour mapper les chemins d’accès de bureau locaux des ressources liées aux URL sur le serveur Experience Manager. Elle se base sur quelques hypothèses :

* Les chemins d’accès aux fichiers placés dans l’application native utilisent un chemin d’accès de bureau global (placé à partir du partage réseau local illustré par l’option [!UICONTROL Reveal]).

* Les chemins sont stockés dans l’enregistrement XMP du fichier par l’application native.

* Experience Manager a extrait l’enregistrement XMP avec les chemins d’accès dans l’enregistrement de métadonnées de la ressource.

* Les chemins d’accès peuvent être associés aux ressources dans Experience Manager. En d’autres termes, les fichiers placés se trouvent également dans Experience Manager sous un chemin d’accès correspondant.

## Nouvelles fonctionnalités et améliorations {#whats-new-added}

Pour en savoir plus, voir [Nouveautés de la version v2.0](introduction.md#whats-new-v2).

**Mises à jour dans la version v2.0.2 de l’application**

Les correctifs de bogues et mises à jour sont les suivants :

* Pour améliorer les performances de chargement, augmentez son accélération dans [!UICONTROL Preferences]. Lorsque ce paramètre est activé, l’application utilise davantage de threads CPU locaux et consomme plus de ressources.

* Correction d’un problème lié au chargement de fichiers lorsque les noms de fichiers ou les chemins d’accès contenaient certains caractères GB18030. <!-- CQ-4283494 -->

* L’option Trier par ordre de pertinence est disponible après le passage à un autre type de tri dans les résultats de la recherche. <!-- CQ-4286874 -->

* L’application de bureau répertorie désormais les sous-dossiers sans avoir à les actualiser explicitement. <!-- CQ-4285711 -->

* (Windows) Correction d’un rare problème d’interface d’application inutilisable sur certains ordinateurs Windows. Les utilisateurs ne peuvent pas cliquer sur l’interface de l’application, car elle semble déformée avec un décalage de la zone de clic des éléments de l’interface. <!-- CQ-4280785 -->

**Mises à jour dans la version v2.0.1 de l’application**

Les correctifs de bogues et mises à jour sont les suivants :

* Option permettant de configurer le répertoire `%Temp%` de façon à ce qu’il corresponde au chemin d’accès à `%APPDATA%`. <!-- CQ-4282665 -->

* Permet aux utilisateurs de se connecter à l’instance Auteur AEM via l’authentification SAML Okta. <!-- CQ-4278134 -->

## Instructions d’installation {#installation-instructions-v2}

Pour savoir comment installer et configurer l’application, voir [Installation de l’appli de bureau Experience Manager](install-upgrade.md).

Si vous effectuez une mise à niveau à partir d’une version précédente de l’appli de bureau Experience Manager, vous devez observer les bonnes pratiques de transition répertoriées dans [Mise à niveau à partir d’une version précédente](install-upgrade.md#upgrade-from-previous-version).

## Remarques importantes sur le fonctionnement de l’application {#how-app-works}

Il est important de comprendre ce qui suit à propos de l’application et de son fonctionnement.

* L’application offre un contrôle total sur les opérations qui nécessitent le transfert complet des fichiers binaires depuis et vers AEM (ouverture, modification, chargement des modifications et chargement des ressources).

   * Si vous souhaitez utiliser la ressource figurant sur le bureau, vous devez explicitement ouvrir, modifier ou télécharger sur votre bureau, que ce soit individuellement, dans un dossier ou par sélection multiple.

   * Si vous souhaitez que les modifications locales apportées aux ressources soient chargées dans AEM, vous devez sélectionner [!UICONTROL Upload Changes], individuellement ou par sélection multiple.

   * L’application n’est pas un client de synchronisation qui synchronise les ressources sur le bureau et AEM.

   * L’application ne fournit pas de partage réseau qui mappe le référentiel AEM en tant que structure de dossiers virtuelle.

* La liste des ressources affichées par l’application est basée sur le statut du référentiel AEM Assets. Les fichiers téléchargés localement puis renommés dans les fichiers locaux ou le dossier de cache ne sont ni affichés ni gérés par l’application.

* Si l’application n’affiche pas les résultats attendus, cliquez sur l’icône d’actualisation dans la barre supérieure.

* Le partage réseau local, qui apparaît lorsque vous utilisez l’action [!UICONTROL Reveal File], n’affiche que les fichiers (et les dossiers) disponibles localement. Les actions [!UICONTROL Reveal File] et [!UICONTROL Reveal Folder] pré-téléchargent les ressources pour afficher les ressources appropriées dans le partage réseau local.

* Le partage réseau local SMB (Mac)/WebDAV (Win) est utilisé lorsqu’une application Adobe Creative Cloud lit les fichiers de ressources liés/placés dans un fichier natif de l’application Creative Cloud.

Le diagramme suivant illustre le flux de ressources et de fichiers allant du cloud au système de fichiers local et vice versa, tel qu’il est initié par les actions de l’utilisateur.

![Flux de ressources allant du serveur AEM aux applications de bureau natives via l’appli de bureau](assets/da20_flow_diagram.png)

## Problèmes connus {#known-issues-v2}

**Problèmes liés à l’interface utilisateur :**

* Parfois, l’interface de l’appli de bureau peut devenir vide. Cliquez avec le bouton droit, puis cliquez sur [!UICONTROL Refresh] pour recharger l’application. Après une telle actualisation, vous démarrez à la racine du référentiel DAM. Les mises à jour ou les états de vos ressources sont conservés. <!-- CQ-4270267 -->

* Difficulté à naviguer dans les dossiers/résultats de recherche sans pavé tactile ni pointeur de souris. Il se peut que la barre de défilement ne s’affiche pas avec les dispositifs de souris sans molette. <!-- CQ-4269947 -->

* Rarement, la barre de progression ne s’affiche pas correctement lorsque la ressource de téléchargement change.

* Après avoir appliqué et supprimé le filtre pour rechercher toutes les ressources modifiées localement, l’application n’amène pas l’utilisateur à ses résultats de recherche ou à la vue de dossiers par laquelle il a commencé. L’application affiche le dossier racine du référentiel DAM.

* Parfois, lorsque vous vous connectez à une URL pour laquelle le serveur AEM n’est pas en cours d’exécution, l’écran de connexion ne répond plus. Quittez l’application et redémarrez-la.

**Problèmes CRUD (Create, Read, Update, and Delete) :**

* L’application tente de télécharger des fichiers même avec des caractères non valides, ce qui peut entraîner l’échec du chargement côté serveur. <!-- CQ-4273652 -->

* Lors du chargement de modifications avec commentaires d’une ressource, les commentaires sont stockés avec la ressource dans AEM, mais ne sont pas visibles en tant que commentaires de contrôle de version. Ce problème est résolu dans AEM 6.4.5 et 6.5.1. Adobe recommande vivement d’installer les derniers Service Packs. <!-- CQ-4268990 -->

* Les transferts de ressources ne peuvent pas être annulés par l’utilisateur. Si vous avez déclenché involontairement un transfert volumineux, quittez l’application et redémarrez-la. <!-- CQ-4278940 -->

**Problèmes de plateforme :**

* Parfois, sous Windows, le statut d’une ressource peut passer immédiatement à [!UICONTROL Edited Locally] après son ouverture, même si vous ne l’avez pas modifié. Cliquez sur [!UICONTROL Refresh] pour mettre le statut à jour.

>[!MORELIKETHIS]
>
>* [Documentation d’AEM as a Cloud Service](https://docs.adobe.com/content/help/fr-FR/experience-manager-cloud-service/landing/home.html)
>* [Documentation d’AEM as a Cloud Service Assets](https://docs.adobe.com/content/help/fr-FR/experience-manager-cloud-service/assets/home.html)
>* [Utilisation de l’appli de bureau Experience Manager](using.md)
>* [Installation et mise à niveau d’une appli de bureau](install-upgrade.md)
>* [Bonnes pratiques et résolution des problèmes](troubleshoot.md)

