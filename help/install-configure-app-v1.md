---
title: Install and configure [!DNL Experience Manager] desktop app version 1.x
description: Installez et [!DNL Experience Manager] desktop app version 1.x to work with [!DNL Assets] configureservers et mappez les ressources à monter en tant que lecteur sur votre bureau.
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.5/ASSETS, SG_EXPERIENCEMANAGER/6.4/ASSETS,SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2893fc1f8aad02e1436a1a281a320e6837487220
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 70%

---


# Install and configure [!DNL Experience Manager] desktop app v1.x {#install-and-configure-aem-desktop-app}

Using the [!DNL Experience Manager] desktop app, the assets within [!DNL Experience Manager] are easily accessible on your local desktop and can be used in any desktop applications. Assets can be easily revealed in Mac Finder or Windows Explorer, opened in desktop applications, and changed locally – the changes are saved back to [!DNL Experience Manager] when you upload and a new version is created in the repository.

Cette intégration permet à différents rôles au sein de l’entreprise de gérer les ressources de manière centralisée dans  Assets, et d’y accéder dans Creative Cloud et d’autres applications, tout en facilitant la conformité avec les diverses normes, y compris le branding.

To use [!DNL Experience Manager] desktop app,

* Ensure that your [!DNL Experience Manager] server version is supported by [!DNL Experience Manager] desktop app. Voir le [tableau de compatibilité](release-notes-of-v1.md#compatibilitymatrix).

* Téléchargez et installez l’application.

* Testez la connexion à l’aide de quelques ressources. Voir [Accès aux ressources et ouverture de ces éléments sur votre ordinateur de bureau](use-app-v1.md#openondesktop).

## Configuration requise, conditions préalables et liens de téléchargement {#system-requirements-prerequisites-and-download-links}

Pour plus d’informations, voir les [[!DNL Experience Manager] Notes de mise à jour de l’appli de bureau ](release-notes-of-v1.md).

## Installation et connexion de l’application au [!DNL Experience Manager] serveur {#install-and-connect-aem-desktop-app-to-aem-server}

Pour plus d’informations, voir [Installation et [!DNL Experience Manager] desktop app to [!DNL Experience Manager] connexion au serveur](use-app-v1.md#installandconnect).

>[!NOTE]
>
>Only one instance of the [!DNL Experience Manager] desktop app can be installed and be active at a time.

## Gestion des fichiers {#file-handling}

Lorsque vous modifiez des fichiers à partir d’un partage réseau monté par l’appli de bureau AEM, les fichiers sont enregistrés à cet emplacement en deux phases. Au cours de la première phase, un fichier est enregistré en local. Un utilisateur peut enregistrer le fichier et continuer à travailler sur celui-ci, sans attendre la fin du transfert.

In the second phase, desktop app uploads the updated file to [!DNL Experience Manager] server after a predefined delay (for example, 30s). Cette opération s’effectue en arrière-plan. Utilisez l’option View Asset Status (Afficher l’état des ressources) pour afficher l’état de l’opération de transfert.

1. Téléchargez une ressource vers  Assets.

1. Click the [!DNL Experience Manager] desktop app icon from the toolbar.

1. Sélectionnez l’option View Asset Status (Afficher le statut des ressources) dans le menu.

1. Dans la boîte de dialogue, examinez le statut de l’opération de chargement.

>[!NOTE]
>
>[!DNL Experience Manager] l’application de bureau peut gérer les ressources jusqu’à 40 Go.

## Connect to an [!DNL Experience Manager] instance behind a dispatcher {#connect-to-an-aem-instance-behind-a-dispatcher}

Les méthodes copy et move de l’API Assets nécessitent que les en-têtes supplémentaires suivantes soient transmises à [!DNL Experience Manager]:

* X-Destination
* X-Depth
* X-Overwrite

[!DNL Experience Manager]L’appli de bureau  se connecte à à l’aide d’une URL qui comprend le port par défaut. [!DNL Experience Manager] Par conséquent, le paramètre `virtualhosts` dans la configuration du Dispatcher doit inclure le numéro de port par défaut. Pour plus d’informations sur la configuration de `virtualhosts`, voir [Identification des hôtes virtuels](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=fr#identifying-virtual-hosts-virtualhosts).

Pour plus d’informations sur la configuration du Dispatcher afin de transmettre ces en-têtes supplémentaires, voir [Spécification des en-têtes HTTP](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=fr#specifying-the-http-headers-to-pass-through-clientheaders).

### Prise en charge des proxys {#proxy-support}

[!DNL Experience Manager]L’appli de bureau  utilise le proxy prédéfini du système pour se connecter à Internet par le biais du protocole HTTPS. L’application ne peut se connecter qu’à l’aide d’un proxy réseau ne nécessitant pas d’authentification supplémentaire.

If you configure or modify proxy server settings for Windows (Internet Options > LAN Settings), restart the [!DNL Experience Manager] desktop app for the changes to take effect.

>[!NOTE]
>
>La configuration du proxy est appliquée uniquement lorsque vous démarrez l’appli de bureau. Fermez et relancez l’application pour que les modifications prennent effet.

Si votre proxy nécessite une authentification, l’équipe informatique peut autoriser l’URL d’Experience Manager Assets dans les paramètres du serveur proxy afin d’autoriser le trafic de l’application.

## Personnalisation de la boîte de dialogue Asset Info (Informations sur les ressources) {#customize-the-asset-info-dialog}

Vous pouvez personnaliser la boîte de dialogue Asset Info (Informations sur les ressources) en recouvrant l’un de ces composants, ou les deux :

* La page de l’interface utilisateur Granite, située à l’adresse `/libs/dam/gui/content/assets/moreinfo`.

* Le composant `/css/javascript` HTL, situé à l’adresse `/libs/dam/gui/components/admin/moreinfo`.

La nature du composant recouvert dépend de la nature de la personnalisation. Pour modifier les composants affichés dans la boîte de dialogue Asset Info (Informations sur les ressources), recouvrez la page de l’interface utilisateur Granite. Pour modifier le contenu HTML, CSS ou JavaScript de la boîte de dialogue, superposez le composant HTML.

## Gestion du cache {#manage-cache}

Sous Windows, le cache se situe à l’emplacement `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\`, où il existe une version codée de l’hôte configuré dans l’appli de bureau AEM. [!DNL Experience Manager] Par exemple, `http://localhost:4502` s’affiche comme suit : `http%3A%2F%2Flocalhost%3A4502%2F`

Sous Mac OS X, un répertoire semblable est situé à l’emplacement suivant : `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`

### Option dans l’application pour gérer le cache {#in-app-option-to-manage-cache}

Vous pouvez contrôler la quantité d’espace disque disponible pour la mise en cache locale. Les artefacts du serveur  Assets sont mis en cache localement pour garantir une expérience plus fluide. Vous pouvez modifier les paramètres par défaut pour répondre à vos besoins. Vous pouvez effacer le cache pour récupérer à nouveau toutes les ressources. Pour définir les options de votre choix, cliquez sur l’icône de l’application, puis sur **[!UICONTROL Advanced]** > **[!UICONTROL Manage Cache]**.

>[!NOTE]
>
>Lorsque vous effacez le cache, les modifications non enregistrées sont conservées. Any assets not checked into [!DNL Experience Manager] server are retained and not deleted.

### Modification de l’emplacement du cache sous Windows {#change-location-of-cache-on-windows}

The default location of the cache for the [!DNL Experience Manager] desktop app is as follows:

* Sous Windows, `%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`.

* Sous Mac, `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`.

`EncodedAEMEndpoint` est l’URL du point de [!DNL Experience Manager] terminaison configuré par l’application. The value is an encoded version of the targeting URL of the [!DNL Experience Manager] server. Par exemple, si l’application cible est `http://localhost:4502`, le nom du répertoire est `http%3A%2F%2Flocalhost%3A4502`. Le chemin d’accès Windows au répertoire du cache dans cet exemple est `%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502`.

Pour faire pointer l’application vers un autre dossier ou lecteur, modifiez son fichier de configuration.

1. Accédez au répertoire d’installation de l’application. L’emplacement par défaut sous Windows est `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop`.

1. Modifiez le fichier Desktop.exe.config d’Adobe Experience Manager à l’aide d’un éditeur de texte.

   Des privilèges d’administrateur sont nécessaires pour enregistrer les modifications apportées à ce fichier.

1. Recherchez la chaîne « ProxyCacheRoot ». Comme vous pouvez le voir, sa valeur est définie sur l’emplacement du cache `%LocalAppData%\Adobe\AssetsCompanion\Cache`. Il vous suffit de définir cette valeur sur n’importe quel chemin d’accès valide.

   >[!NOTE]
   >
   >L’application crée automatiquement un sous-répertoire *&lt;Point d’entrée AEM codé>* ; ce comportement n’est pas configurable.

>[!MORELIKETHIS]
* [ [!DNL Experience Manager] Présentation de l’appli de bureau ](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app.html?lang=fr).
* [Application [!DNL Experience Manager] de bureau](use-app-v1.md).
* [ [!DNL Experience Manager] Résolution des problèmes liés à une application](troubleshoot-app-v1.md)de bureau.

