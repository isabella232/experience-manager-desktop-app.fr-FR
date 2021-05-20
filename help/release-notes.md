---
title: Notes de mise à jour de l’appli de bureau [!DNL Adobe Experience Manager]
description: Détails des mises à jour, améliorations, nouvelles fonctionnalités, compatibilité et liens de téléchargement pour l’appli de bureau [!DNL Adobe Experience Manager] .
mini-toc-levels: 1
feature: Appli de bureau, Informations sur la version
exl-id: e058e7a2-fcc8-4ad1-899e-20695db6bc72
source-git-commit: ac533db59b2a5c64243b762f4b77b3148c4f1867
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 100%

---

# Notes de mise à jour de l’application de bureau [!DNL Adobe Experience Manager] {#release-notes-v2}

Les informations de mise à jour de la dernière version de l’appli de bureau 2.1 (2.1.2.0) sont les suivantes. La date de publication est le 26 mars 2021. Il s’agit d’une version mineure avec une amélioration.

Les **versions de [!DNL Experience Manager] prises en charge** sont les suivantes :

* [!DNL Experience Manager] as a [!DNL Cloud Service]. Voir les [notes de mise à jour](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/home.html?lang=fr).
* [!DNL Experience Manager] 6.5.0 ou version ultérieure, sur Adobe Managed Services (AMS) ou On-Premise. Consultez les [notes de mise à jour du Service Pack](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/service-pack/sp-release-notes.html?lang=fr).
* [!DNL Experience Manager] 6.4.4 ou version ultérieure, sur Adobe Managed Services (AMS) ou On-Premise. Consultez les [notes de mise à jour du Service Pack](https://experienceleague.adobe.com/docs/experience-manager-64/release-notes/sp-release-notes.html?lang=fr).
* [!DNL Experience Manager] 6.4.0 à 6.4.3 avec le [package de compatibilité](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) installé, sur Adobe Managed Services (AMS) ou On-Premise.
* [!DNL Experience Manager] 6.3 (avec le package de compatibilité)
* [!DNL Experience Manager] 6.3.3.1 ou plus récent avec le [package de compatibilité](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) installé. L’appli de bureau n’est pas prise en charge pour les versions d’[!DNL Experience Manager] 6.3.3.0 ou antérieures.

L’appli de bureau [!DNL Adobe Experience Manager] est disponible avec les **systèmes d’exploitation** suivants :

* macOS X 10.14 ou version ultérieure, avec les correctifs de bogues les plus récents. [Les ordinateurs Mac avec processeurs Apple](https://support.apple.com/fr-fr/HT211814) ne sont pas encore pris en charge.
* Windows 10 avec les derniers Service Packs et correctifs.

Les **URL de téléchargement** pour les systèmes d’exploitation pris en charge sont les suivantes :

| Système d’exploitation | [!DNL Experience Manager] as a [!DNL Cloud Service] | [!DNL Experience Manager] 6.x |
|---|---|---|
| macOS 64 bits | [Lien de téléchargement](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.2.0.dmg) | [Lien de téléchargement](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.2.0.dmg) |
| Windows 64 bits | [Lien de téléchargement](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.2.0.exe) | [Lien de téléchargement](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.2.0.exe) |
| Windows 32 bits | [Lien de téléchargement](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.2.0.exe) | [Lien de téléchargement](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.2.0.exe) |

>[!NOTE]
>
>Windows 7 n’est plus pris en charge. Consultez [l’article sur la fin du support de Windows 7](https://support.microsoft.com/fr-fr/help/4057281/windows-7-support-ended-on-january-14-2020).

<!-- The version of the app you plan to install on your local machine requires a specific [!DNL Adobe Experience Manager] server version/additional server-side components (service packs, hot fixes, or feature packs). Contact your [!DNL Experience Manager] administrator for help.
-->

## Prise en charge de différents types de ressources et de fichiers {#support-for-file-types}

L’application prend en charge les ressources stockées dans [!DNL Experience Manager] qui représentent un fichier binaire pour ses opérations de base. L’ouverture de fichiers dans l’application de bureau native dépend de l’association du système d’exploitation des types de fichiers spécifiques (par exemple, PNG ou JPG) à des applications spécifiques (par exemple, Mac Preview ou Adobe Photoshop).

Certains types de fichiers prennent en charge le placement de ressources liées dans le fichier binaire. L’application pré-télécharge les ressources liées si la ressource est présente dans le référentiel [!DNL Experience Manager] lorsque ces fichiers binaires sont ouverts à l’aide de l’appli de bureau. Les types de fichiers actuellement pris en charge sont les suivants :

* Fichiers [!DNL Adobe InDesign] (format INDD)
* Fichiers [!DNL Adobe Illustrator] (format AI)
* Fichiers [!DNL Adobe Photoshop] (format PS)

Cette fonctionnalité est prise en charge avec les versions 2018 d’[!DNL Adobe Creative Cloud] et 2019 d’[!DNL Adobe Creative Cloud] de l’application ci-dessus. L’application utilise une approche heuristique et de la meilleure correspondance pour mapper les chemins d’accès de bureau locaux des ressources liées aux URL sur le serveur [!DNL Experience Manager]. Elle se base sur quelques hypothèses :

* Les chemins d’accès aux fichiers placés dans l’application native utilisent un chemin d’accès de bureau global (placé à partir du partage réseau local illustré par l’option [!UICONTROL Reveal]).

* Les chemins sont stockés dans l’enregistrement XMP du fichier par l’application native.

* [!DNL Experience Manager] a extrait l’enregistrement XMP avec les chemins d’accès dans l’enregistrement de métadonnées de la ressource.

* Les chemins d’accès peuvent être associés aux ressources dans [!DNL Experience Manager]. En d’autres termes, les fichiers placés se trouvent également dans [!DNL Experience Manager] sous un chemin d’accès correspondant.

## Nouvelles fonctionnalités, améliorations et corrections de bogues {#what-is-new}

Pour en savoir plus, voir [Nouveautés de la version v2.0](introduction.md#whats-new-v2).

**Mise à jour dans la version v2.1.2.0 de l’application**

* Une nouvelle option pour [!UICONTROL Clear Cookies] est ajoutée au menu principal de l’application. Elle permet de résoudre les problèmes potentiels de connexion, par exemple lors du changement de connexion d’un serveur à un autre. Voir la section [Effacer les cookies avant de se connecter](/help/troubleshoot.md#cannot-login-cookies-issue).

**Mise à jour dans la version v2.1.1.0 de l’application**

* Un des paramètres avancés permet à l’application d’émuler le comportement de l’application v1.10 lors du chargement de dossiers. Dans la version 1.10, les noms de nœuds créés dans le référentiel respectent les espaces et la casse des noms de dossier fournis par l’utilisateur. Le comportement par défaut de la version 2.1 reste le même, c’est-à-dire qu’il remplace les espaces dans les noms de dossiers par un tiret dans le nom du nœud du référentiel et le convertit en minuscules. Consultez [les préférences de l’application](/help/install-upgrade.md#set-preferences).

**Mise à jour dans la version v2.1.0.0 de l’application**

* Pour charger des fichiers, les utilisateurs peuvent désormais faire glisser les fichiers ou les dossiers sur l’interface de l’application, directement depuis l’Explorateur Windows ou le Finder Mac. Cette opération s’ajoute à l’option de chargement précédemment disponible dans l’application. <!-- CQ-4309527 -->

**Mise à jour dans la version v2.0.3 de l’application**

Le bogue corrigé dans la version actuelle est le suivant :

* Correction du problème de connexion des utilisateurs de l’applications sous Windows qui tentaient d’accéder au référentiel DAM sur [!DNL Adobe Experience Manager] 6.5.5.0.

**Mises à jour dans la version v2.0.2 de l’application**

Les correctifs de bogues et mises à jour sont les suivants :

* Le paramètre d’accélération de chargement est désormais disponible pour améliorer les performances de chargement. Lorsque ce paramètre est activé, l’application charge plus rapidement en utilisant davantage de threads de CPU locaux et de ressources.

* Le chargement de ressources dont les noms de fichier ou les chemins d’accès contiennent certains caractères GB18030 a été résolu. <!-- CQ-4283494 -->

* L’option Trier par ordre de pertinence est disponible après le passage à un autre type de tri dans les résultats de la recherche. <!-- CQ-4286874 -->

* L’application de bureau répertorie désormais les sous-dossiers sans avoir à les actualiser explicitement. <!-- CQ-4285711 -->

* (Windows) Correction d’un rare problème d’interface d’application inutilisable sur certains ordinateurs Windows. Les utilisateurs ne peuvent pas cliquer sur l’interface de l’application, car elle semble déformée avec un décalage de la zone de clic des éléments de l’interface. <!-- CQ-4280785 -->

**Mises à jour dans la version v2.0.1 de l’application**

Les correctifs de bogues et mises à jour sont les suivants :

* Option permettant de configurer le répertoire `%Temp%` de façon à ce qu’il corresponde au chemin d’accès à `%APPDATA%`. <!-- CQ-4282665 -->

* Permet aux utilisateurs de se connecter à l’instance Auteur d’[!DNL Experience Manager] via l’authentification SAML Okta. <!-- CQ-4278134 -->

## Instructions d’installation {#installation-instructions-v2}

Pour savoir comment installer et configurer l’application, voir [Installation [!DNL Experience Manager]  de l’appli de bureau](install-upgrade.md).

Si vous effectuez une mise à niveau à partir d’une version précédente de l’appli de bureau [!DNL Experience Manager], vous devez observer les bonnes pratiques de transition répertoriées dans [Mise à niveau à partir d’une version précédente](install-upgrade.md#upgrade-from-previous-version).

## Remarques importantes sur le fonctionnement de l’application {#how-app-works}

Il est important de comprendre ce qui suit à propos de l’application et de son fonctionnement.

* L’application offre un contrôle total sur les opérations qui nécessitent le transfert complet des fichiers binaires depuis et vers [!DNL Experience Manager] (ouverture, modification, chargement des modifications et chargement des ressources).

   * Si vous souhaitez utiliser la ressource figurant sur le bureau, vous devez explicitement ouvrir, modifier ou télécharger sur votre bureau, que ce soit individuellement, dans un dossier ou par sélection multiple.

   * Si vous souhaitez que les modifications locales apportées aux ressources soient chargées dans [!DNL Experience Manager], vous devez sélectionner [!UICONTROL Upload Changes], individuellement ou par sélection multiple.

   * L’application n’est pas un client de synchronisation qui synchronise les ressources sur le bureau et [!DNL Experience Manager].

   * L’application ne fournit pas de partage réseau qui mappe le référentiel [!DNL Experience Manager] en tant que structure de dossiers virtuelle.

* La liste des ressources affichées par l’application est basée sur le statut du référentiel Assets. Les fichiers téléchargés localement puis renommés dans les fichiers locaux ou le dossier de cache ne sont ni affichés ni gérés par l’application.

* Si l’application n’affiche pas les résultats attendus, cliquez sur l’icône d’actualisation dans la barre supérieure.

* Le partage réseau local, qui apparaît lorsque vous utilisez l’action [!UICONTROL Reveal File], n’affiche que les fichiers (et les dossiers) disponibles localement. Les actions [!UICONTROL Reveal File] et [!UICONTROL Reveal Folder] pré-téléchargent les ressources pour afficher les ressources appropriées dans le partage réseau local.

* Le partage réseau local SMB (Mac)/WebDAV (Win) est utilisé lorsqu’une application Adobe Creative Cloud lit les fichiers de ressources liés/placés dans un fichier natif de l’application Creative Cloud.

Le diagramme suivant illustre le flux de ressources et de fichiers allant du cloud au système de fichiers local et vice versa, tel qu’il est initié par les actions de l’utilisateur.

![Flux de ressources allant du serveur [!DNL Experience Manager] aux applications de bureau natives via l’appli de bureau](assets/da20_flow_diagram.png)

## Problèmes connus {#known-issues-v2}

**Problèmes liés à l’interface utilisateur :**

* Parfois, l’interface de l’appli de bureau peut devenir vide. Cliquez avec le bouton droit, puis cliquez sur [!UICONTROL Refresh] pour recharger l’application. Après une telle actualisation, vous démarrez à la racine du référentiel DAM. Les mises à jour ou les états de vos ressources sont conservés. <!-- CQ-4270267 -->

* Difficulté à naviguer dans les dossiers/résultats de recherche sans pavé tactile ni pointeur de souris. Il se peut que la barre de défilement ne s’affiche pas avec les dispositifs de souris sans molette. <!-- CQ-4269947 -->

* Rarement, la barre de progression ne s’affiche pas correctement lorsque la ressource de téléchargement change.

* Après avoir appliqué et supprimé le filtre pour rechercher toutes les ressources modifiées localement, l’application n’amène pas l’utilisateur à ses résultats de recherche ou à la vue de dossiers par laquelle il a commencé. L’application affiche le dossier racine du référentiel DAM.

* Parfois, lorsque vous vous connectez à une URL pour laquelle le serveur [!DNL Experience Manager] n’est pas en cours d’exécution, l’écran de connexion ne répond plus. Quittez l’application et redémarrez-la.

**Problèmes CRUD (Create, Read, Update et Delete) :**

* L’application tente de télécharger des fichiers même avec des caractères non valides, ce qui peut entraîner l’échec du chargement côté serveur. <!-- CQ-4273652 -->

* Lors du chargement de modifications avec commentaires d’une ressource, les commentaires sont stockés avec la ressource dans [!DNL Experience Manager], mais ne sont pas visibles en tant que commentaires de contrôle de version. Ce problème est résolu dans les versions 6.4.5 d’[!DNL Experience Manager] et 6.5.1 d’[!DNL Experience Manager]. Adobe recommande vivement d’installer les derniers Service Packs. <!-- CQ-4268990 -->

* Les transferts de ressources ne peuvent pas être annulés par l’utilisateur. Si vous avez déclenché involontairement un transfert volumineux, quittez l’application et redémarrez-la. <!-- CQ-4278940 -->

**Problèmes de plateforme :**

* Parfois, sous Windows, le statut d’une ressource peut passer immédiatement à [!UICONTROL Edited Locally] après son ouverture, même si vous ne l’avez pas modifié. Cliquez sur [!UICONTROL Refresh] pour mettre le statut à jour.

>[!MORELIKETHIS]
>
>* Documentation d’[[!DNL Experience Manager] as a [!DNL Cloud Service] ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=fr)
>* Documentation d’[[!DNL Experience Manager] as a [!DNL Cloud Service] [!DNL Assets] ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/home.html?lang=fr)
>* [Comment utiliser l’appli de bureau [!DNL Experience Manager] ](using.md)
* [Installation et mise à niveau d’une appli de bureau](install-upgrade.md)
* [Bonnes pratiques et résolution des problèmes](troubleshoot.md)

