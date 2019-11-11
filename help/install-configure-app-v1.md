---
title: Installation et configuration de l’application de bureau AEM version 1.x
seo-title: Installation et configuration de l’application de bureau AEM version 1.x
description: Installez et configurez l’application de bureau AEM version 1.x pour qu’elle fonctionne avec les serveurs AEM Assets et mappez les ressources à monter en tant que lecteur sur votre bureau.
seo-description: Installez et configurez l’application de bureau AEM version 1.x pour qu’elle fonctionne avec les serveurs AEM Assets et mappez les ressources à monter en tant que lecteur sur votre bureau.
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-03571942740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ce29042aff6d4caea0e7b8a56673d4bfed03a45

---


# Installation et configuration de l’application de bureau AEM v1.x {#install-and-configure-aem-desktop-app}

Installez et configurez l’application de bureau AEM pour qu’elle fonctionne avec les serveurs AEM Assets et téléchargez les ressources sur votre système de fichiers local. Pour utiliser l’application de bureau AEM, procédez comme suit :

* Vérifiez que la version de votre serveur AEM est prise en charge par l’application de bureau AEM. Voir le [tableau de compatibilité](release-notes-of-v1.md#compatibilitymatrix).
* Téléchargez et installez l’application.
* Testez la connexion à l’aide de quelques ressources. See [Access and open assets on your desktop](use-app-v1.md#openondesktop).

## Configuration requise, conditions préalables et liens de téléchargement {#system-requirements-prerequisites-and-download-links}

For detailed information, see the [AEM desktop app release notes](release-notes-of-v1.md).

## Install and connect AEM desktop app to AEM server {#install-and-connect-aem-desktop-app-to-aem-server}

For details, see [Install and connect AEM desktop app to AEM server](use-app-v1.md#installandconnect).

>[!NOTE]
>
>Une seule instance de l’application de bureau AEM peut être installée et être active à la fois.

## Prise en charge des proxys {#proxy-support}

L’application de bureau AEM utilise le proxy prédéfini du système pour se connecter à Internet via HTTPS. L’application ne peut se connecter qu’à l’aide d’un proxy réseau ne nécessitant pas d’authentification supplémentaire.

Si vous configurez ou modifiez les paramètres du serveur proxy pour Windows (Options Internet &gt; Paramètres LAN), redémarrez l’application de bureau AEM pour que les modifications prennent effet.

Si votre proxy nécessite une authentification, l’équipe informatique peut mettre l’URL d’AEM Assets sur liste blanche dans les paramètres du serveur proxy afin d’autoriser le trafic de l’application.

## Gestion des fichiers {#file-handling}

Lorsque vous modifiez un fichier d’un emplacement de partage réseau monté par l’application de bureau, les fichiers sont enregistrés à cet emplacement en deux phases. Au cours de la première phase, un fichier est enregistré en local. Un utilisateur peut enregistrer le fichier et continuer à travailler sur celui-ci, sans attendre la fin du transfert.

Dans la deuxième phase, l’application de bureau télécharge le fichier mis à jour vers le serveur AEM après un délai prédéfini (par exemple, 30 s). Cette opération s’effectue en arrière-plan. Utilisez l’option View Asset Status (Afficher l’état des ressources) pour afficher l’état de l’opération de transfert. 

1. Téléchargez une ressource vers AEM Assets.
1. Cliquez/appuyez sur l'icône de l'application de bureau AEM dans la barre d'outils.
1. Sélectionnez l’option View Asset Status (Afficher l’état des ressources) dans le menu.
1. Dans la boîte de dialogue, consultez l’état de l’opération de transfert.

>[!NOTE]
>
>L’application de bureau AEM peut gérer les ressources jusqu’à 40 Go.

## Connexion à une instance AEM derrière un Dispatcher {#connect-to-an-aem-instance-behind-a-dispatcher}

Les méthodes Copy et Move de l’API Assets nécessitent que les en-têtes supplémentaires suivantes soient transmises à AEM :

* X-Destination
* X-Depth
* X-Overwrite

L’application de bureau AEM se connecte à AEM à l’aide d’une URL qui comprend le port par défaut. Therefore, the *virtualhosts* setting in the dispatcher configuration should include the default port number. For more information around virtualhosts configuration, see [Identifying Virtual Hosts](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#identifying-virtual-hosts-virtualhosts).

For additional information on configuring the dispatcher to pass through these additional headers, see [Specifying the HTTP Headers](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#specifying-the-http-headers-to-pass-through-clientheaders).

## Personnalisation de la boîte de dialogue Asset Info (Informations sur les ressources){#customize-the-asset-info-dialog}

Vous pouvez personnaliser la boîte de dialogue Informations sur le fichier en superposant un ou les deux composants suivants :

* The Granite user interface page at `/libs/dam/gui/content/assets/moreinfo`
* Le composant HTL `/css/javascript` à `/libs/dam/gui/components/admin/moreinfo`

La nature du composant recouvert dépend de la nature de la personnalisation. Pour modifier les composants affichés dans la boîte de dialogue Asset Info (Informations sur les ressources), recouvrez la page de l’interface utilisateur Granite. Pour modifier le contenu HTML/CSS/JavaScript de la boîte de dialogue, recouvrez le composant HTL.

## Gestion du cache {#manage-cache}

On Windows, the cache is at `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\`, where is an encoded version of the AEM host configured in the desktop app. Par exemple, `http://localhost:4502` apparaît comme `http%3A%2F%2Flocalhost%3A4502%2F`.

On Mac OS X, a similar directory is at `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`.

### Option dans l’application pour gérer le cache {#in-app-option-to-manage-cache}

Vous pouvez contrôler la quantité d’espace disque disponible pour la mise en cache locale. Les artefacts du serveur AEM Assets sont mis en cache localement pour garantir une expérience plus fluide. Vous pouvez modifier les paramètres par défaut pour répondre à vos besoins. Vous pouvez effacer le cache pour récupérer à nouveau toutes les ressources. To set the desired options, click the application's icon and click **[!UICONTROL Advanced]** &gt; **[!UICONTROL Manage Cache]**. ****

>[!NOTE]
>
>Lorsque vous effacez le cache, les modifications non enregistrées sont conservées. Toutes les ressources non archivées dans le serveur AEM sont conservées.

### Modification de l’emplacement du cache sous Windows {#change-location-of-cache-on-windows}

L’emplacement par défaut du cache de l’application de bureau AEM est :

* Windows: `%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`
* Mac: `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`

`EncodedAEMEndpoint` est l’URL du point de fin AEM configuré par l’application de bureau AEM. La valeur est une version codée de l’URL de ciblage du serveur AEM. For example, if the application is targeting `http://localhost:4502`, the directory name is `http%3A%2F%2Flocalhost%3A4502`. Le chemin d'accès Windows au répertoire du cache dans cet exemple est %LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502.

Pour faire pointer l’application vers un autre dossier ou lecteur, modifiez son fichier de configuration.

1. Accédez au répertoire d’installation de l’application. L’emplacement par défaut sous Windows est `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop`.
1. Modifiez le fichier Desktop.exe.config d’Adobe Experience Manager à l’aide d’un éditeur de texte.

   Des privilèges d’administrateur sont requis pour enregistrer les modifications dans ce fichier.

1. Recherchez la chaîne « ProxyCacheRoot ». Comme vous pouvez le voir, sa valeur est définie sur l’emplacement du cache « %LocalAppData%\Adobe\AssetsCompanion\Cache ». Il vous suffit de définir cette valeur sur n’importe quel chemin d’accès valide.

   >[!NOTE]
   >
   >The app automatically creates an *&lt;Encoded AEM Endpoint&gt;* subdirectory; this behavior is not configurable.

## Ressources supplémentaires {#additional-resources}

* [Présentation de l’application de bureau AEM](https://helpx.adobe.com/experience-manager/kt/eseminars/ccoo-aem-desktop-app.html)
* [Utiliser l’application de bureau AEM](use-app-v1.md)

* [Comprendre l'archivage et l'extraction avec l'application de bureau AEM](https://helpx.adobe.com/experience-manager/kt/assets/using/checkin-checkout-technical-video-understand.html)
* [Utilisation d’une application de bureau avec AEM Assets](https://helpx.adobe.com/experience-manager/kt/assets/using/checkin-checkout-technical-video-understand.html)
* [Dépannage de l'application de bureau AEM](troubleshoot-app-v1.md)