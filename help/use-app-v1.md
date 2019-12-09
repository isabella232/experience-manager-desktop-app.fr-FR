---
title: Utilisation de l’appli de bureau AEM version 1.x
description: Découvrez comment utiliser l’appli de bureau Adobe Experience Manager version 1.x et optimiser votre utilisation des ressources du bureau.
uuid: 55057617-89de-43cd-8419-1252a42ab2fb
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 39d7bcad-d7b0-4978-a790-4cb68b8a7d6a
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ad5337c8e1697d0a37d3020d25802dc1d732f320

---


# Utilisation de l’appli de bureau AEM v1.x {#use-aem-desktop-app-v1x}

À l’aide de l’appli, les ressources d’AEM sont facilement accessibles sur votre ordinateur local et peuvent être utilisées dans n’importe quelle application de bureau. Les ressources peuvent être facilement affichées dans le Finder de Mac ou l’Explorateur Windows, ouvertes dans des applications de bureau et modifiées localement ; les modifications sont réenregistrées dans AEM avec une nouvelle version créée dans le référentiel.

Cette intégration permet à différents rôles au sein de l’entreprise de gérer les ressources de manière centralisée dans AEM Assets, et d’y accéder dans Creative Cloud et d’autres applications, tout en facilitant la conformité avec les diverses normes, y compris la valorisation de marque.

Les tâches clés que vous effectuez à l’aide de l’appli de bureau AEM v1 sont les suivantes :

* [Connexion à un serveur AEM](#installandconnect)

* [Ouverture directe de ressources sur l’ordinateur de bureau](#openondesktop)
* [Modification et extraction de ressources à partir de l’ordinateur de bureau](#workonassets)

* [Chargement en masse de ressources et de dossiers](#bulkupload)

Pour les pratiques recommandées, voir les [Bonnes pratiques d’utilisation de l’application](best-practices-for-v1.md). Si vous rencontrez des problèmes lors de l’utilisation de l’application, consultez la page traitant du [dépannage de l’appli de bureau AEM](troubleshoot-app-v1.md).

>[!NOTE]
>L’appli de bureau AEM a été lancée avec la version 6.1 d’AEM, sous le nom d’AEM Assets Companion App.

## Points de contact de l’appli de bureau AEM dans le processus de création {#aem-desktop-app-touch-points-in-the-creative-workflow}

L’application AEM Desktop, ainsi que les ressources AEM, s’intègrent à votre processus créatif et offre les points de contact suivants.

![Points de contact de l’appli de bureau AEM dans le processus de création](assets/aem_desktopapp_workflow.png)

Points de contact de l’appli de bureau AEM dans le processus de création

## Installation de l’appli de bureau AEM et connexion de l’application au serveur AEM {#installandconnect}

Pour pouvoir commencer à créer ou modifier les ressources de création, connectez l’application de bureau au serveur AEM Assets pour télécharger et charger des ressources dans le référentiel. Effectuez les tâches suivantes :

1. [Installez l’application](#installapp).
1. [Définissez vos préférences](#inapppref) et vos informations de connexion.
1. [Connectez-vous au serveur AEM](#connect) et montez le référentiel de ressources comme lecteur local.
1. [Activez les actions de bureau](#desktopactions) sur le serveur AEM.

L’appli de bureau AEM établit une connexion HTTPS au serveur AEM afin de transférer vos ressources de manière sécurisée.

>[!NOTE]
>Pour une partie ou l’ensemble de la procédure d’installation et de configuration, il se peut que vous deviez demander l’aide de votre administrateur AEM ou de votre administrateur système.

### Installation de l’application {#installapp}

Pour utiliser l’appli de bureau AEM, vérifiez que votre version du serveur AEM est prise en charge par celle-ci. Téléchargez le fichier d’installation approprié (binaire) pour votre système d’exploitation (Mac ou Windows) et installez ensuite l’application.

Une configuration détaillée peut s’avérer nécessaire en fonction des préférences de votre système et de votre réseau. Pour plus d’informations, voir [Installation et configuration de l’appli de bureau AEM](install-configure-app-v1.md).

1. Rendez-vous sur la [page de téléchargement de l’appli de bureau AEM](https://helpx.adobe.com/experience-manager/kb/download-companion-app.html) et téléchargez le fichier binaire approprié à votre système d’exploitation.
1. Exécutez le fichier d’installation téléchargé et suivez les instructions affichées à l’écran pour installer l’application.

   >[!NOTE]
   >Une seule instance de l’appli de bureau AEM peut être installée et active à la fois.

### Présentation des options et des préférences dans l’application {#inapppref}

L’application accepte des paramètres pour se connecter aux serveurs AEM et s’en déconnecter, afficher l’état des transferts, gérer le cache local et ainsi de suite. Les paramètres par défaut sont opérationnels pour un utilisateur ordinaire de l’application. Vous pouvez les régler avec précision pour tirer pleinement parti de l’application et de l’intégration dans le serveur AEM. Les différents paramètres sont décrits ci-dessous de manière détaillée.

**Explore Assets (Explorer les ressources)** Ouvrez le lecteur local sur lequel est monté le référentiel AEM Assets. En d’autres termes, explorez les ressources qui sont désormais disponibles sur votre ordinateur local.

**View asset status (Afficher le statut des ressources)** Lorsque des ressources modifiées sont chargées ou que de nouvelles ressources sont ajoutées au référentiel AEM Assets, l’application procède à leur chargement en arrière-plan. Cela garantit la fluidité des opérations, sans qu’il faille patienter jusqu’à la fin du transfert, en particulier pour les ressources de grande taille. Vous pouvez enregistrer vos modifications en local et ne plus vous en soucier. En fonction de la bande passante disponible, l’application peut prendre un certain temps pour envoyer ces ressources au serveur. Vous pouvez vérifier l’état du transfert, avec d’autres informations de base.

**Options** Cliquez/appuyez sur Options dans la barre d’état de l’appli de bureau AEM pour accéder aux paramètres permettant de lancer l’application au démarrage de votre système, de vous connecter au serveur AEM au lancement de l’appli et de modifier la lettre du lecteur local sur lequel AEM Assets est disponible après le montage.

**Advanced &gt; Manage cache (Avancé &gt; Gérer le cache)** Vous pouvez contrôler la quantité d’espace disque disponible pour la mise en cache locale. Les artefacts du serveur AEM Assets sont mis en cache localement pour garantir une expérience plus fluide. Vous pouvez modifier les paramètres par défaut pour répondre à vos besoins. Vous pouvez effacer le cache pour récupérer à nouveau toutes les ressources. Lorsque vous effacez le cache, les modifications non enregistrées sont conservées. Toutes les ressources non archivées dans le serveur AEM sont conservées.

### Connexion à un serveur AEM {#connect}

L’application prend en charge la configuration du proxy sous Mac et Windows. La configuration est lue au démarrage de l’application. Si vous modifiez les paramètres du proxy, redémarrez l’application pour que les modifications soient prises en compte.

>[!NOTE]
>
>Si vous modifiez les paramètres du proxy, redémarrez l’application pour que les modifications soient prises en compte. Sans cela, l’application continue à utiliser le serveur proxy précédemment configuré.

1. Lancez l’appli de bureau AEM. Pour mapper votre instance AEM à l’application, spécifiez votre serveur AEM au format suivant `https://[aem-server-url]:[port]`.

   ![Authentification sous Mac et spécification de l’URL du serveur AEM](assets/aem_desktop_app_server_url.png)

1. Dans l’écran de connexion, indiquez le nom d’utilisateur et le mot de passe de votre instance. Pour spécifier une autre instance AEM, sélectionnez l’option **[!UICONTROL Alternate Login URL]**.

   ![Saisie des informations d’identification du serveur AEM dans l’écran de connexion de l’appli de bureau AEM](assets/chlimage_1-2.png)

### Activation des actions de bureau dans l’interface web d’AEM {#desktopactions}

À partir de l’interface utilisateur AEM Assets ouverte dans un navigateur, vous pouvez explorer l’emplacement des ressources ou extraire et en ouvrir une en vue de la modifier dans votre application de bureau. Ces options, qui sont appelées actions de bureau, ne sont pas activées par défaut. Procédez comme suit pour les activer.

1. Dans la console Assets, cliquez/appuyez sur l’icône **Utilisateur** dans la barre d’outils.
1. Cliquez/appuyez sur **[!UICONTROL My Preferences]** pour afficher la boîte de dialogue **[!UICONTROL Preferences]**.
1. Dans la boîte de dialogue User Preference (Préférences utilisateur), sélectionnez **[!UICONTROL Show Desktop Actions For Assets]**. Cliquez/appuyez sur **[!UICONTROL Accept]**.

   ![Activation de la case à cocher Afficher les actions de bureau pour les ressources afin d’activer les actions de bureau](assets/chlimage_1-3.png)

   Cocher la case Show Desktop Actions For Assets pour activer les actions de bureau

## Accès aux ressources et ouverture de ces éléments sur votre ordinateur de bureau  {#openondesktop}

>[!NOTE]
>Sous Windows, le [paramètre par défaut de Windows 7](https://support.microsoft.com/en-us/kb/2668751) empêche l’appli de bureau AEM de gérer les ressources de plus de 50 Mo.

### Affichage de l’emplacement des ressources mappées à partir de l’interface web AEM {#reveal-the-location-of-mapped-assets-from-aem-web-interface}

Après avoir mappé le référentiel AEM Assets sur votre lecteur local, vous pouvez activer des icônes supplémentaires, ainsi que la fonction de téléchargement de dossiers, afin qu’elles s’affichent pour les ressources et les dossiers mappés.

1. Ouvrez l’interface d’AEM Assets et placez le pointeur sur un dossier ou une ressource afin d’afficher les actions de bureau sous la forme d’actions rapides dans le mode Carte.

   ![Dans l’interface utilisateur Assets, ouvrez le menu des actions rapides pour afficher les actions de bureau](assets/chlimage_1-4.png)

   Dans l’interface utilisateur Assets, ouvrez le menu des actions rapides pour afficher les actions de bureau

   Ces actions de bureau sont également disponibles lorsque vous cliquez/appuyez sur l’icône **Desktop Actions** (Actions sur le bureau) dans la barre d’outils après la sélection de la ressource ou dans la barre d’outils de la page de la ressource.

1. Pour ouvrir la ressource dans l’application de bureau associée à l’extension de fichier spécifique, cliquez/appuyez sur l’action rapide **Open on desktop** (Ouvrir sur le bureau) ![Icône Open on Desktop](assets/aemassets_icon_openondesktop.png).

   Vous pouvez également sélectionner **Open** (Ouvrir) dans le menu **Desktop Actions** (Actions sur le Bureau) de la barre d’outils.

1. Cliquez/appuyez sur l’action rapide **Reveal** (Afficher) ![Icône Reveal](assets/aemassets_reveal_icon.png) pour rechercher une ressource particulière dans votre système de fichiers local.

   Vous pouvez également sélectionner **Reveal** (Afficher) dans le menu **Desktop Actions** (Actions sur le Bureau) de la barre d’outils.

### Ouverture d’AEM Assets à partir du Finder ou de l’Explorateur {#open-aem-assets-from-the-finder-or-the-explorer}

Sous Mac, sélectionnez Ouvrir dans le menu contextuel pour ouvrir une ressource via AEM Desktop.

Pour les fichiers Adobe InDesign (INDD), sélectionnez **[!UICONTROL Open]** dans le menu contextuel. Lorsque vous cliquez sur cette option, l’application télécharge les ressources liées sur votre système de fichiers local, puis ouvre le fichier INDD dans Adobe InDesign. Cette méthode garantit que les ressources requises sont disponibles en local lors de la modification du fichier INDD.

Sous Windows, sélectionnez Ouvrir sur le web dans le menu contextuel pour ouvrir la ressource. Dans la fenêtre Asset Status (Statut de la ressource), cliquez/appuyez sur ![Icône Open on Desktop](assets/aemassets_icon_openondesktop.png) pour ouvrir la ressource.

![Options de menu contextuel permettant d’accéder à des ressources et de les ouvrir à l’aide de l’appli de bureau AEM](assets/aem_desktopapp_mac_context_menu.png)

Options de menu contextuel permettant d’accéder à des ressources et de les ouvrir à l’aide de l’appli de bureau AEM

### Explication des états de ressources  {#understand-the-asset-statuses}

| ![Icône de l’appli par défaut Windows](assets/win_default.png) | L’application est connectée au serveur, et toutes les ressources sont synchronisées. |
|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| ![Icône de l’appli Windows désactivée](assets/win_disabled.png) | L’application est lancée, mais n’est pas connectée au serveur. Certaines ressources peuvent être en attente de synchronisation. |
| ![Icône de synchronisation des fichiers Windows](assets/win_sync.png) | La synchronisation des ressources est en cours. Les fichiers sont en cours de transfert ou de téléchargement. Vous pouvez afficher les statuts précis et suspendre les transferts dans la fenêtre Asset Status (Statut de la ressource). |
| ![Icône de reconnexion Windows](assets/win_refresh.png) | L’application effectue une tentative de reconnexion. Les problèmes réseau peuvent entraîner sa déconnexion. |

## Utilisation de vos ressources {#workonassets}

### Extraction de ressources à partir de l’interface web AEM {#check-out-assets-from-the-aem-web-interface}

AEM Assets permet d’extraire des ressources pour les modifier et de les ré-archiver après y avoir apporté les modifications. Après avoir extrait une ressource, vous seul pouvez la modifier, l’annoter, la publier, la déplacer ou la supprimer. Le fait d’extraire une ressource entraîne son verrouillage et empêche les autres utilisateurs d’effectuer l’une de ces opérations. Vous avez besoin d’un accès en écriture à ces ressources pour être en mesure de les extraire ou de les archiver.

Pour extraire des ressources à partir de l’interface web AEM, deux méthodes sont possibles. Pour obtenir des informations détaillées sur la première méthode, voir [Archivage et extraction de fichiers à partir de l’interface utilisateur Assets](https://helpx.adobe.com/in/experience-manager/6-4/assets/using/check-out-and-submit-assets.html). Pour la deuxième méthode, suivez la procédure ci-dessous pour extraire et ouvrir la ressource quand l’appli de bureau AEM est installée.

1. Ouvrez l’interface d’AEM Assets et placez le pointeur sur un dossier ou une ressource afin d’afficher les actions de bureau sous la forme d’actions rapides dans le mode Carte.

   ![Option des propriétés dans le mode Carte](assets/chlimage_1-4.png)

   Ces actions de bureau sont également disponibles lorsque vous cliquez/appuyez sur l’icône Desktop Actions (Actions sur le Bureau) dans la barre d’outils après la sélection de la ressource ou dans la barre d’outils de la page de la ressource.

1. Pour ouvrir la ressource, cliquez/appuyez sur l’action rapide Open on desktop (Ouvrir sur le Bureau) ![Icône Open on Desktop](assets/aemassets_icon_openondesktop.png).

   Vous pouvez également sélectionner Open (Ouvrir) dans le menu Desktop Actions (Actions sur le Bureau) de la barre d’outils.

   >[!NOTE]
   >Lorsque vous modifiez un fichier qui est simplement ouvert, mais pas extrait, les autres utilisateurs ne savent pas que vous êtes en train de mettre à jour une ressource.

1. Pour ouvrir une ressource en vue de la modifier dans une application Adobe Creative Cloud, cliquez/appuyez sur l’action rapide Edit desktop (Modifier le Bureau) ![Icône Edit Desktop](assets/aemassets_icon_editdesktop.png). Cette option extrait également la ressource en vue de la modifier. Après avoir procédé aux modifications, archivez la ressource pour mettre à jour les modifications dans AEM Assets.

   Vous pouvez également sélectionner Edit (Modifier) dans le menu Desktop Actions (Actions sur le Bureau) de la barre d’outils.

1. Sélectionnez l’option de menu Open (Ouvrir). Les ressources sélectionnées sont ouvertes en mode d’aperçu.
1. Pour modifier les ressources, sélectionnez l’option Edit (Modifier). Les ressources sont ouvertes en mode d’édition.

### Extraction de ressources sous Mac   {#check-out-assets-on-mac}

L’application permet d’extraire des fichiers de ressource pour empêcher d’autres utilisateurs de modifier les fichiers sur lesquels vous travaillez.

1. Dans le menu contextuel de Mac, sélectionnez Open AEM Assets Folder (Ouvrir le dossier AEM Assets) pour ouvrir le Finder.

   ![Options de menu contextuel permettant d’accéder à des ressources et de les ouvrir à l’aide de l’appli de bureau AEM](assets/aem_desktopapp_mac_context_menu.png)

   Options de menu contextuel permettant d’accéder à des ressources et de les ouvrir à l’aide de l’appli de bureau AEM

1. Accédez à la ressource à extraire.

   ![Ouverture dans le menu contextuel d’AEM Assets sous Mac](assets/chlimage_1-5.png)

1. Cliquez avec le bouton droit sur la ressource, puis choisissez More Assets Info (Plus d’infos sur la ressource) dans le menu contextuel.
1. Dans la boîte de dialogue Asset Info (Informations sur les ressources), cliquez/appuyez sur l’icône Checkout (Extraire) pour extraire la ressource. L'icône Passage en caisse bascule vers l'icône d'arrivée lorsque vous cliquez ou appuyez dessus.

   ![Accès à la ressource pour l’extraire](assets/chlimage_1-6.png)

1. Pour archiver le fichier afin qu’il soit accessible aux autres utilisateurs, cliquez/appuyez sur l’icône d’archivage dans la boîte de dialogue Informations sur le fichier.

### Extraction de ressources sous Windows {#check-out-assets-on-windows}

L’application permet d’extraire des fichiers de ressource pour empêcher d’autres utilisateurs de modifier les fichiers sur lesquels vous travaillez.

1. Dans le menu contextuel, sélectionnez Explorer les ressources pour ouvrir l’Explorateur.
1. Dans l’Explorateur, accédez à l’emplacement de la ressource à extraire.

   ![Changement de l’icône Checkout (Extraire)](assets/chlimage_1-7.png)

1. Cliquez avec le bouton droit sur la ressource, puis choisissez Ouvrir sur le web dans le menu contextuel.
1. Dans la boîte de dialogue Asset Info (Informations sur les ressources), cliquez/appuyez sur l’icône Extraire. L'icône Passage en caisse bascule vers l'icône d'arrivée.

   ![Changement de l’icône Checkout (Extraire)](assets/chlimage_1-8.png)

1. Consultez la ressource dans l’Explorateur. L’icône de verrouillage sur la ressource ![Icône Asset lock](assets/aemassets_icon_lockcheckout.png) indique que vous avez extrait cette dernière.

   >[!NOTE]
   >Cette icône peut apparaître après quelques minutes. L’appli de bureau AEM met en cache les ressources en vue d’un accès rapide. La mise à jour de l’état Verrouillé peut donc prendre un certain temps.

1. To check in the asset so it is available to other users, click/tap the check-in icon in the **Asset Info** dialog.

### Archivage d’une ressource à l’aide du Finder ou de l’Explorateur et en utilisant l’interface web   {#check-in-an-asset-using-finder-or-explorer-and-using-web-interface}

Une fois la modification des ressources effectuée, enregistrez ces dernières dans votre application de bureau. Dans le menu contextuel, sélectionnez Plus d’informations sur les ressources, puis cliquez/appuyez sur Archiver.

Les ressources sont transférées vers le serveur AEM. Vous pouvez éventuellement vérifier le statut du transfert en sélectionnant View Asset Status (Afficher le statut des ressources) à partir de l’icône de la barre d’état.

![Fenêtre d’état de chargement et de transfert de fichiers de l’appli de bureau AEM](assets/aem_desktopapp_upload_status.png)

Vous pouvez également archiver une ressource à partir de l’interface web AEM. Cliquez/appuyez sur les ressources extraites ou sélectionnez-les. From the toolbar, click/tap the check in icon ![check-in icon](assets/aemassets_icon_checkin.png).

### Chargement en masse de ressources et de dossiers vers le serveur AEM {#bulkupload}

L’appli de bureau AEM permet de télécharger un dossier entier de ressources à partir de votre répertoire de fichiers local vers AEM Assets. Ainsi, toutes les ressources dans le dossier sont téléchargées en masse au lieu d’avoir à les télécharger une par une.

1. Depuis l’IU Assets, cliquez/appuyez sur **Créer** dans la barre d’outils, puis sélectionnez **Dossier de chargement** dans le menu.
1. Accédez au dossier à télécharger et sélectionnez-le.
1. Cliquez/appuyez sur OK. La boîte de dialogue Assets Status (Statut des ressources) affiche le statut du chargement.

   ![Consultation du statut du chargement dans la fenêtre Asset Status (Statut de la ressource)](assets/aem_desktopapp_bulkupload_status.png)

   Consultation du statut du chargement dans la fenêtre Asset Status (Statut de la ressource)

   >[!NOTE]
   >Vous pouvez suspendre ou annuler manuellement le chargement en cliquant/appuyant sur l’icône appropriée.

1. Une fois le dossier transféré, fermez la boîte de dialogue et accédez à l’interface utilisateur Assets. Le dossier transféré s’affiche dans l’interface web.

Notez qu’il est *déconseillé* de copier et de coller ou de faire glisser un grand nombre de fichiers/dossiers imbriqués depuis votre disque local dans le Finder ou l’Explorateur dans la zone de partage réseau mappée par l’appli de bureau AEM. Cette opération s’avère beaucoup moins fiable que la fonctionnalité Upload Folder (Charger un dossier) décrite ci-dessus.

Si vous préférez utiliser l’ordinateur de bureau, une autre solution consiste à sélectionner les fichiers/dossiers que vous souhaitez charger vers AEM dans le Finder ou l’Explorateur, à les copier dans le Presse-papiers du système, à accéder au dossier cible dans la zone de partage réseau et enfin à sélectionner Paste Assets (Coller les ressources) dans le menu contextuel de l’appli de bureau AEM. Ce faisant, l’appli de bureau AEM commence à charger les ressources collées de la même manière que la fonctionnalité Upload Folder (Charger un dossier) décrite ci-dessus.

>[!MORELIKETHIS]
>
>* [Présentation de l’appli de bureau AEM](https://helpx.adobe.com/experience-manager/kt/eseminars/ccoo-aem-desktop-app.html)
>* [Présentation de l’archivage/l’extraction avec l’appli de bureau AEM](https://helpx.adobe.com/experience-manager/kt/assets/using/checkin-checkout-technical-video-understand.html)
>* [Résolution des problèmes relatifs à l’application de bureau AEM](troubleshoot-app-v1.md)

