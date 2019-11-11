---
title: Notes de mise à jour de l’application de bureau AEM
seo-title: Notes de mise à jour de l’application de bureau AEM
description: Détails de la version, améliorations, nouvelles fonctionnalités, compatibilité et liens de téléchargement pour l’application de bureau AEM v1.x.
seo-description: Détails de la version, améliorations, nouvelles fonctionnalités, compatibilité et liens de téléchargement pour l’application de bureau AEM v1.x.
uuid: b783c3f8-aa1e-4c05-b687-5894909769f5
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 3052549b-fe75-44fb-a55e-5cc612868f54
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b74a3ff5c9a25ee1433dd661a1bce677271a5ebe

---


# AEM desktop app Release Notes {#release-notes-v2}

| Produits | Application de bureau Adobe Experience Manager (AEM) |
|---------------|--------------------------------------------------------------------|
| Version de l’application (révision) | 2.0 (2.0.0.4) |
| Versions d’AEM prises en charge | AEM 6.5, AEM 6.4, AEM 6.3 (avec package de compatibilité) |
| Type | Version majeure |
| Date de publication | 30 août 2019 (Mac), 9 septembre 2019 (Windows) |
| URL de téléchargement | [MacOS 64 bits](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-osx-2.0.0.4.dmg); [Windows 64 bits](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win64-2.0.0.4.exe); [Windows 32 bits](https://download.macromedia.com/aem-assets-companion-app/aem-desktop-win32-2.0.0.4.exe) |

## Configuration requise et conditions préalables {#system-requirements-and-prerequisites-v2}

L’application de bureau AEM est compatible avec les systèmes d’exploitation suivants :

* Mac OS X 10.10 ou version ultérieure, avec les correctifs de bogues les plus récents.
* Windows7 et Windows 10 avec les Service Packs et les correctifs de bogues les plus récents.

L’application fonctionne avec les versions AEM suivantes, qu’elles soient déployées sur site ou sur les services gérés Adobe (AMS) :

* [AEM 6.5.0](https://helpx.adobe.com/experience-manager/6-5/release-notes.html) ou version ultérieure
* [AEM 6.4.4](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) ou version ultérieure
* AEM 6.4.0 - 6.4.3 avec package [de compatibilité](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)
* AEM 6.3.3.1 et versions ultérieures avec package [de compatibilité](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support)
* Pour AEM 6.3, aucun [Service Packs n’est planifié](https://helpx.adobe.com/experience-manager/maintenance-releases-roadmap.html). Adobe recommande d’effectuer la mise à niveau vers une version ultérieure d’AEM.

La version de l’application que vous prévoyez d’installer sur votre ordinateur local requiert une version spécifique du serveur Adobe Experience Manager/des composants supplémentaires côté serveur (Service Packs, correctifs ou Feature Packs). Contactez votre administrateur AEM pour obtenir de l’aide.

### Prise en charge de différents types de fichier et de fichier {#support-for-file-types}

L’application prend en charge les ressources stockées dans AEM qui représentent un fichier binaire pour ses opérations de base. L’ouverture de fichiers dans l’application de bureau native dépend de l’association du système d’exploitation des types de fichiers spécifiques, tels que PNG ou JPG, à des applications spécifiques, telles que Mac Preview ou Adobe Photoshop.

Certains types de fichiers prennent en charge le placement de fichiers liés dans le fichier binaire. L’application prétélécharge les actifs liés si le fichier est présent dans le référentiel AEM lorsque de tels fichiers binaires sont ouverts à l’aide de l’application de bureau. Les types de fichiers actuellement pris en charge sont les suivants :

* Fichiers Adobe InDesign (format INDD)
* Fichiers Adobe Illustrator (format AI)
* Fichiers Adobe Photoshop (format PS)

Cette fonctionnalité est prise en charge avec Adobe Creative Cloud 2018 et les versions Creative Cloud 2019 de l’application ci-dessus. L’application utilise une approche heuristique et de la meilleure correspondance pour mapper les chemins d’accès locaux des fichiers liés aux URL sur le serveur AEM. Elle repose sur quelques hypothèses :

* Les chemins d’accès aux fichiers placés dans l’application native utilisent un chemin d’accès global pour ordinateur de bureau (placé à partir du partage réseau local illustré par l’option "Révéler").
* Les chemins sont stockés dans l’enregistrement XMP du fichier par l’application native.
* AEM a extrait l’enregistrement XMP avec les chemins d’accès à l’enregistrement de métadonnées de la ressource.
* Les chemins peuvent être associés aux ressources dans AEM (ce qui signifie que les fichiers importés se trouvent également dans AEM sous un chemin correspondant).

## New features and enhancements {#whats-new-added}

Pour en savoir plus, voir [Nouveautés de l’application](introduction.md#whats-new-v2).

## Instructions d’installation {#installation-instructions-v2}

Pour savoir comment installer et configurer l’application, voir [Installation de l’application](install-upgrade.md)de bureau AEM.

Si vous effectuez une mise à niveau à partir d’une application de bureau AEM précédente, vous devez suivre les bonnes pratiques de transition répertoriées à la [mise à niveau à partir de la version](install-upgrade.md#upgrade-from-previous-version)précédente.

## Remarques importantes sur le fonctionnement de l’application {#how-app-works}

Il est important de comprendre ce qui suit au sujet de l’application et de son fonctionnement.

* L’application offre un contrôle total sur les opérations qui nécessitent le transfert complet des fichiers binaires depuis et vers AEM (ouverture, modification, transfert des modifications et transfert des ressources).
   * Si vous souhaitez utiliser le fichier sur le bureau, vous devez explicitement ouvrir, modifier ou télécharger sur votre bureau, que ce soit individuellement, dans un dossier ou par sélection multiple.
   * Si vous souhaitez que les modifications locales des ressources soient téléchargées vers AEM, vous devez les sélectionner [!UICONTROL Upload Changes], individuellement ou par sélection multiple.
   * L’application n’est pas un "client de synchronisation" qui synchronise les ressources sur le bureau et AEM.
   * L’application ne fournit pas de partage réseau qui mappe le référentiel AEM en tant que structure de dossiers virtuels.
* La liste des actifs affichée par l’application est basée sur l’état du référentiel AEM Assets. Les fichiers téléchargés localement, puis renommés dans les fichiers locaux ou le dossier cache ne sont ni affichés ni gérés par l’application.
* Si l’application n’affiche pas les résultats attendus, cliquez sur l’icône Actualiser dans la barre supérieure.
* Le partage réseau local, illustré lorsque vous utilisez [!UICONTROL Reveal File] l’action, affiche uniquement les fichiers (et les dossiers) disponibles localement. [!UICONTROL Reveal File] et [!UICONTROL Reveal Folder] prétélécharge les ressources pour permettre l’affichage des ressources appropriées dans le partage réseau local.
* Le partage de réseau local SMB (Mac)/WebDAV (Win) est utilisé lorsqu’une application Adobe Creative Cloud lit les fichiers liés/placés dans un fichier natif de l’application Creative Cloud.

Le diagramme suivant illustre le flux de ressources et de fichiers du cloud vers le système de fichiers local et vice versa, tel qu’il est initié par les actions de l’utilisateur.

![Flux de ressources du serveur AEM vers des applications de bureau natives via une application de bureau](assets/do-not-localize/da20_flow_diagram.png)

## Problèmes connus {#known-issues-v2}

**Problèmes d’interface utilisateur :**
* Parfois, l’interface de l’application de bureau peut devenir vide. Cliquez avec le bouton droit de la souris et cliquez [!UICONTROL Refresh] pour charger à nouveau l’application. Une telle actualisation réinitialise l’état de l’application et vous démarrez à l’écran de bienvenue à la racine du référentiel DAM. <!-- CQ-4270267 -->
* Difficile de naviguer dans les dossiers/résultats de recherche sans un pavé tactile ou une molette de la souris. La barre de défilement peut ne pas s’afficher avec les périphériques de la souris sans la molette de la souris. <!-- CQ-4269947 -->
* La barre de progression ne s’affiche pas souvent correctement lorsque le fichier de téléchargement change.
* Après avoir appliqué et supprimé le filtre pour rechercher toutes les ressources modifiées localement, l’application n’amène pas les utilisateurs à la vue des résultats de recherche ou des dossiers avec lesquels ils ont commencé. L’application affiche le dossier racine du référentiel DAM.
* Parfois, lorsque vous vous connectez à une URL pour laquelle le serveur AEM n’est pas en cours d’exécution, l’écran de connexion ne répond plus. Quittez l’application et redémarrez-la.

**Problèmes CRUD (Créer, Lire, Mettre à jour et Supprimer) :**
* L’application tente de télécharger des fichiers même avec des caractères non valides, ce qui peut entraîner l’échec du transfert côté serveur. <!-- CQ-4273652 -->
* Lors du téléchargement de modifications dans un fichier avec des commentaires, les commentaires sont stockés avec le fichier dans AEM mais ne sont pas visibles en tant que commentaires de contrôle de version (résolus dans AEM 6.4.5, 6.5.1). <!-- CQ-4268990 -->
* Les transferts de ressources ne peuvent pas être annulés par l’utilisateur. Si vous avez déclenché un transfert important involontaire, quittez l’application et redémarrez-la. <!-- CQ-4278940 -->

**Problèmes de plateforme :**
* Parfois, sous Windows, l’état d’un fichier peut changer immédiatement [!UICONTROL Edited Locally] après son ouverture, même si vous ne l’avez pas modifié. Cliquez sur [!UICONTROL Refresh] pour mettre à jour.

>[!MORELIKETHIS]
>
>* [Documentation AEM 6.5](https://helpx.adobe.com/support/experience-manager/6-5.html)
>* [Documentation d’AEM Assets 6.5](https://docs.adobe.com/content/help/en/experience-manager-64/assets/home.html)
>* [Utiliser l’application de bureau AEM](using.md)
>* [Installation et mise à niveau d’une application de bureau](install-upgrade.md)
>* [Recommandations et conseils de dépannage](troubleshoot.md)

