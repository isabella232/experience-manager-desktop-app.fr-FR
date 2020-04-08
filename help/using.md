---
title: Utilisation de l’appli de bureau Adobe Experience Manager
description: Découvrez comment installer et tirer parti de l’appli de bureau Adobe Experience Manager pour utiliser des ressources DAM Adobe Experience Manager directement depuis votre bureau Windows ou Mac. Découvrez les bonnes pratiques et les informations de dépannage.
uuid: 55057617-89de-43cd-8419-1252a42ab2fb
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 39d7bcad-d7b0-4978-a790-4cb68b8a7d6a
mini-toc-levels: 1
translation-type: tm+mt
source-git-commit: e706fe5fe148deff519cadc72b724572f11ddf3c

---


# Utilisation de l’appli de bureau Adobe Experience Manager {#use-aem-desktop-app-v2}

Utilisez l’appli de bureau Adobe Experience Manager (AEM) pour accéder facilement aux ressources DAM Adobe Experience Manager situées sur votre poste de travail local et les utiliser dans n’importe quelle application de bureau. Vous pouvez ouvrir les ressources dans des applications de bureau et les modifier localement, puis charger les modifications dans Experience Manager avec contrôle de version pour partager les mises à jour avec d’autres utilisateurs. Vous pouvez également charger de nouveaux fichiers et des hiérarchies de dossiers vers Experience Manager, créer des dossiers et supprimer des ressources ou des dossiers de DAM Experience Manager.

L’intégration permet à différents rôles de l’organisation de gérer les ressources de manière centralisée dans Experience Manager Assets et d’accéder aux ressources sur un poste de travail local dans les applications natives sous Windows ou Mac OS.

Lorsque vous ouvrez l’application après vous être déconnecté ou lorsque vous vous connectez pour la première fois, fournissez l’URL de votre serveur Experience Manager. Cliquez sur Connect (Connecter). Indiquez vos informations d’identification pour connecter l’application au serveur.

L’appli de bureau Experience Manager vous permet d’effectuer les tâches clés suivantes :

![Workflows et tâches pouvant être effectués avec l’appli de bureau Experience Manager](assets/aem_desktop_app_usecases_v2.png "Workflows et tâches pouvant être effectués avec l’appli de bureau Adobe Experience Manager")
Téléchargez [ce](assets/aem_desktop_app_usecases_print.pdf) fichier PDF prêt à être imprimé.

## Fonctionnement de l’appli de bureau {#how-app-works2}

Avant de commencer à utiliser l’application, vous devez comprendre le [Fonctionnement de l’application](release-notes.md#how-app-works). Familiarisez-vous également avec les termes suivants :

* **[!UICONTROL Desktop Actions]** : à partir de l’interface web Assets, dans un navigateur, vous pouvez explorer l’emplacement des ressources ou extraire et ouvrir une ressource en vue de la modifier dans votre application de bureau native. Ces actions sont disponibles à partir de l’interface web et utilisent les fonctionnalités des applications de bureau. Voir [Comment activer les actions de bureau](using.md#desktopactions-v2).

* Le statut du fichier est **[!UICONTROL Cloud Only]** : ces ressources ne sont pas téléchargées sur l’ordinateur local et ne sont disponibles que sur le serveur Experience Manager.

* Le statut du fichier est **[!UICONTROL Available locally]** : les ressources sont téléchargées et disponibles sur l’ordinateur local en l’état. Les ressources ne sont pas modifiées.

* Le statut du fichier est **[!UICONTROL Edited locally]** : ces ressources sont modifiées localement et les modifications restent à charger vers le serveur Experience Manager. Après le chargement, le statut passe à [!UICONTROL Available locally]. Voir [Modification de ressources](using.md#edit-assets-upload-updated-assets).

* Le statut du fichier est **[!UICONTROL Editing conflict]** : si vous et d’autres utilisateurs modifiez une ressource simultanément, l’application indique qu’un conflit de modification s’est produit. L’application propose également des options pour conserver ou ignorer vos modifications. Découvrez [comment éviter les conflits de modification](using.md#adv-workflow-collaborate-avoid-conflicts).

* Le statut du fichier est **[!UICONTROL Modified remotely]** : l’application indique si une ressource que vous avez téléchargée est modifiée sur le serveur Experience Manager. L’application permet également de télécharger la dernière version et de mettre à jour votre copie locale. Découvrez [comment éviter les conflits de modification](using.md#adv-workflow-collaborate-avoid-conflicts).

* **[!UICONTROL Check-out]** : si vous modifiez un fichier ou envisagez de le modifier, faites-le passer au statut d’extraction. Une icône de verrouillage apparaît sur la ressource dans l’application et dans l’interface web d’AEM. Cette icône indique aux autres utilisateurs d’éviter de modifier simultanément la même ressource, car cela entraînerait un conflit de modification.

* **[!UICONTROL Check-in]** : marquez la ressource comme étant sécurisée pour que d’autres utilisateurs puissent la modifier sans provoquer de conflit de modification. Lorsque vous chargez vos modifications, l’icône de verrouillage disparaît automatiquement. Activer le statut d’archivage supprime également l’icône de verrouillage, bien qu’il soit recommandé de ne pas effectuer d’archivage manuel sans charger les modifications. Si vous annulez vos modifications, activez manuellement le statut d’archivage.

* Action **[!UICONTROL Open]** : ouvrez simplement la ressource pour la prévisualiser dans l’application native. Il n’est pas recommandé de modifier la ressource à l’aide de cette action, car cette dernière n’extrait pas la ressource et d’autres utilisateurs peuvent apporter des modifications, ce qui provoque des conflits de modification.

* Action **[!UICONTROL Edit]** : utilisez l’action pour modifier l’image. Le fait de cliquer sur l’action [!UICONTROL Edit] extrait automatiquement la ressource et ajoute une icône de verrouillage à la ressource. Après avoir cliqué sur Edit (Modifier), si vous ne souhaitez pas modifier la ressource, cliquez sur [!UICONTROL Toggle check-in]. Pour supprimer, renommer ou déplacer des ressources dans la hiérarchie de dossiers DAM AEM, utilisez les actions de l’interface web d’AEM et non l’action de modification.

* Action **[!UICONTROL Download]** : téléchargez la ressource sur votre ordinateur local. Vous pouvez télécharger les ressources maintenant et les modifier ultérieurement et travailler hors ligne et charger les modifications ultérieurement. Les fichiers sont téléchargés dans un dossier de cache sur votre système de fichiers.

* Action **[!UICONTROL Reveal File]** ou **[!UICONTROL Reveal Folder]** : tandis que les ressources sont téléchargées vers un dossier de cache local, l’application imite un lecteur réseau local et fournit un chemin d’accès local pour chaque ressource. Pour découvrir ce chemin d’accès, utilisez l’option d’affichage appropriée dans l’application. Une action d’affichage est requise pour placer des ressources dans l’application Creative Cloud. Voir [Placement de ressources](using.md#place-assets-in-native-documents).

* Action **[!UICONTROL Open In Web]** : pour afficher la ressource dans l’interface web d’AEM, ouvrez-la sur le web. Vous pouvez initier d’autres processus à partir de l’interface d’AEM, tels que la mise à jour de métadonnées ou la découverte de ressources.

* Action **[!UICONTROL Delete]** : supprimez la ressource du référentiel DAM AEM. L’action supprime la copie d’origine de la ressource sur le serveur AEM. Si vous souhaitez uniquement ignorer les modifications apportées à la ressource locale, voir [Ignorer les modifications](using.md#edit-assets-upload-updated-assets).

* **[!UICONTROL Upload Changes]** : l’appli de bureau ne charge la ressource mise à jour que si vous la chargez explicitement sur le serveur AEM. Lorsque vous enregistrez vos modifications, celles-ci ne sont enregistrées que sur votre ordinateur local. Lorsque vous chargez la ressource, elle est automatiquement archivée et l’icône de verrouillage disparaît. Voir [Modification de ressources](using.md#edit-assets-upload-updated-assets).

## Activation des actions de bureau dans l’interface web d’AEM {#desktopactions-v2}

À partir de l’interface utilisateur Assets ouverte dans un navigateur, vous pouvez explorer l’emplacement des ressources ou extraire et ouvrir une ressource pour la modifier dans votre application de bureau. Ces options, qui sont appelées [!UICONTROL Desktop Actions], ne sont pas activées par défaut. Pour les activer, procédez comme suit.

1. Dans la console Assets, cliquez/appuyez sur l’icône **[!UICONTROL User]** dans la barre d’outils.
1. Cliquez/appuyez sur **[!UICONTROL My Preferences]** pour afficher la boîte de dialogue **[!UICONTROL Preferences]**.
1. Dans la boîte de dialogue Préférences utilisateur, sélectionnez **[!UICONTROL Show Desktop Actions For Assets]**. Cliquez/appuyez sur **[!UICONTROL Accept]**.

   ![Activation de la case à cocher Afficher les actions de bureau pour les ressources afin d’activer les actions de bureau](assets/chlimage_1-3.png)

   Cocher la case [!UICONTROL Show Desktop Actions For Assets] pour activer les actions de bureau

## Parcourir, rechercher et prévisualiser des ressources {#browse-search-preview-assets}

Vous pouvez parcourir, rechercher et prévisualiser les ressources disponibles dans le référentiel AEM, le tout depuis l’application de bureau. Essayez les options suivantes dans l’application :

1. Accédez à un dossier et affichez des informations de base sur les ressources disponibles dans ce dossier, ainsi que de petites vignettes de toutes les ressources.

   ![Accès aux dossiers et fichiers DAM](assets/browse_folder_da2.png "Accès aux dossiers et fichiers DAM")

1. Pour afficher davantage d’informations et une vignette plus grande d’une ressource spécifique, cliquez sur le nom de fichier de la ressource.

   ![Afficher un aperçu plus grand d’une ressource et des actions](assets/large_preview_actions_da2.png "Afficher un aperçu plus grand d’une ressource et des actions")

1. Cliquez sur **[!UICONTROL Open]** ou **[!UICONTROL Edit]** pour télécharger le fichier localement et l’afficher uniquement ou pour le modifier dans l’application native, respectivement.
1. Recherchez à l’aide de mots-clés une ressource associée dans le référentiel AEM. Utilisez `?` et `*` comme caractères génériques. Ces caractères génériques remplacent un caractère unique ou plusieurs caractères, respectivement. Filtrez et triez les résultats selon vos besoins.

   ![Exemple de recherche utilisant un caractère générique astérisque](assets/search_wildcard_da2.png "Exemple de recherche utilisant un caractère générique astérisque")

   ![Autre exemple de recherche utilisant un caractère générique astérisque](assets/search_wildcard2_da2.png "Autre exemple de recherche utilisant un caractère générique astérisque")

>[!NOTE]
>
>L’application affiche les ressources en faisant correspondre les critères de recherche dans plusieurs champs de métadonnées et pas uniquement le titre ou le nom de fichier de la ressource.

## Téléchargement de ressources {#download-assets}

Vous pouvez télécharger les ressources sur votre système de fichiers local. L’application récupère les ressources du serveur AEM et enregistre la même copie sur votre système de fichiers local.

Cliquez sur ![Icône More options](assets/do-not-localize/more2_da2.png) pour afficher les options, puis sur ![Icône Download](assets/do-not-localize/download_cloud_da2.png) pour télécharger.

![Option de téléchargement pour une ressource](assets/download_option_da2.png "Option de téléchargement pour une ressource")

>[!NOTE]
>
>Lors du téléchargement ou du chargement d’un fichier volumineux ou de plusieurs fichiers, l’application désactive les actions sur les ressources et les dossiers. Les actions sont disponibles lorsque le téléchargement ou le chargement est terminé.

Le téléchargement de plusieurs ressources peut entraîner des performances médiocres si la taille de la file d’attente est importante ou si vous rencontrez un problème réseau. En outre, vous pouvez sans le savoir placer en file d’attente de nombreuses ressources à télécharger lorsque vous téléchargez un dossier. Pour éviter les longs délais d’attente, l’application limite le nombre de ressources téléchargées en une seule fois. Pour savoir comment configurer cette fonctionnalité, voir [Définition des préférences](install-upgrade.md#set-preferences). Même en dessous de cette limite, l’application peut parfois rechercher une confirmation avant de télécharger un dossier apparemment volumineux.

![L’appli confirme le téléchargement d’un nombre relativement important de ressources](assets/download_confirmation_da2.png "L’appli confirme le téléchargement d’un nombre relativement important de ressources")

Si un ou des dossiers sont sélectionnés et téléchargés, l’application télécharge uniquement les ressources stockées directement dans le ou les dossiers dans AEM. Elle ne télécharge pas automatiquement les ressources des sous-dossiers.

## Ouvrir des ressources sur votre bureau {#openondesktop-v2}

Vous pouvez ouvrir les ressources distantes pour les afficher dans l’application native. Les ressources sont téléchargées dans un dossier local et lancées dans l’application native associée au format de fichier. Vous pouvez changer l’application native pour ouvrir des types de fichiers (extensions) spécifiques sous Mac ou Windows.

Cliquez sur **[!UICONTROL Open]** dans le menu de ressource. La ressource est téléchargée localement et ouverte dans l’application native. Vérifiez la progression du téléchargement et la vitesse de transfert des ressources volumineuses dans la barre d’état.

<!-- ![Download progress bar for large-sized assets](assets/download_status_bar_da2.png "Download progress bar for large-sized assets")
-->

>[!NOTE]
>
>Si les modifications attendues ne sont pas reflétées dans l’application, cliquez sur l’icône Actualiser ![Icône Actualiser](assets/do-not-localize/refresh.png) ou cliquez avec le bouton droit de la souris sur l’interface de l’application, puis cliquez sur **[!UICONTROL Refresh]**. Les actions ne sont pas disponibles lorsque des téléchargements ou des chargements plus volumineux sont en cours.

Pour ouvrir le dossier de téléchargement local d’une ressource, cliquez sur ![Icône More actions](assets/do-not-localize/more2_da2.png), puis sur l’action ![ ](assets/do-not-localize/reveal_action2_da2.png)Icône Afficher **[!UICONTROL Reveal File]**.

## Utiliser ou placez des ressources dans des documents natifs {#place-assets-in-native-documents}

Dans certains cas (par exemple, lorsque vous importez un fichier dans un document natif), vous accédez à un fichier dans l’Explorateur Windows ou le Finder Mac. Pour accéder à l’emplacement de système de fichiers du fichier téléchargé localement, utilisez l’option ![Icône Afficher](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]**.

![Action Afficher le fichier pour une ressource](assets/revealfile_action_da2.png "Action Afficher le fichier pour une ressource")

Cliquez sur **[!UICONTROL Reveal File]**, ou sur **[!UICONTROL Reveal Folder]** sur un dossier, pour ouvrir l’Explorateur Windows ou le Finder Mac avec le fichier ou le dossier présélectionné sur votre ordinateur local. Cette option est utile, par exemple, pour placer les fichiers AEM dans les applications natives qui prennent en charge le placement ou la liaison de fichiers locaux. Pour savoir comment placer des fichiers dans Adobe InDesign, voir [Placement de graphiques](https://helpx.adobe.com/fr/indesign/using/placing-graphics.html).

L’action **[!UICONTROL Reveal File]** ouvre un partage réseau local qui affiche uniquement les ressources disponibles localement (c’est-à-dire les ressources qui ont été affichées, téléchargées ou ouvertes/modifiées à l’aide de l’application). Le partage réseau local ne charge aucune modification dans AEM. Pour charger les modifications, utilisez explicitement les actions **[!UICONTROL Upload Changes]** ou **[!UICONTROL Upload]** dans l’application.

>[!NOTE]
>
>Pour une compatibilité descendante avec l’appli de bureau AEM v1.x, les fichiers affichés sont diffusés à partir d’un partage réseau local, exposant uniquement les fichiers disponibles en local. Les chemins d’accès aux fichiers affichés sont identiques à ceux créés par l’application v1.x.

>[!CAUTION]
>
>N’utilisez pas l’option **[!UICONTROL Reveal File]** pour modifier des ressources dans des applications natives. Utilisez plutôt les actions **[!UICONTROL Edit]**. Pour en savoir plus, voir [Processus avancé : collaborer sur les mêmes fichiers et éviter les conflits de modification](#adv-workflow-collaborate-avoid-conflicts).

## Modifier des ressources et charger des ressources mises à jour dans AEM {#edit-assets-upload-updated-assets}

Ouvrez les ressources à modifier lorsque vous souhaitez effectuer des modifications et chargez les ressources mises à jour sur le serveur AEM. Pour éviter tout conflit avec les modifications d’autres utilisateurs, utilisez l’application pour ouvrir une session de modification. Avant de commencer à effectuer des modifications, assurez-vous que la ressource ne comporte pas d’icône de verrouillage, c’est-à-dire qu’elle n’est pas en train d’être modifiée par un autre utilisateur.

Pour modifier une ressource, recherchez-la ou accédez à son emplacement. Cliquez sur ![Icône Plus](assets/do-not-localize/more2_da2.png) puis sur **[!UICONTROL Edit]**.

Utilisez **[!UICONTROL Toggle Check-out]** pour verrouiller la ressource afin d’éviter des conflits avec les modifications d’autres utilisateurs dans les deux cas suivants :

* Vous avez commencé à modifier une ressource sans d’abord l’extraire (vous l’avez simplement ouverte).
* Vous vous préparez à modifier une ressource et ne souhaitez pas que d’autres personnes le fassent.

Une fois les modifications effectuées, l’application affiche le statut **[!UICONTROL Edited Locally]** pour les ressources modifiées. Toutes les modifications enregistrées dans les ressources sont en local uniquement jusqu’à ce que vous les chargiez dans AEM. Pour charger une ressource spécifique ou quelques ressources une par une, cliquez sur **[!UICONTROL Upload Changes]** dans les options d’une ressource. Une version de la ressource est alors créée dans AEM. L’interface web d’AEM Assets vous permet d’afficher l’historique des ressources dans la [vue de journal](https://helpx.adobe.com/fr/experience-manager/6-5/assets/using/activity-stream.html).

![Option de chargement des modifications dans l’appli](assets/upload_changes_single1_da2.png "Option de chargement des modifications dans l’appli")

![Option de chargement des modifications lors de l’affichage d’un grand aperçu d’une ressource](assets/upload_changes_single2_da2.png "Option de chargement des modifications lors de l’affichage d’un grand aperçu d’une ressource")

Pour découvrir les bonnes pratiques en matière d’édition collaborative, voir [Processus avancé : collaborer sur les mêmes fichiers et éviter les conflits de modification](#adv-workflow-collaborate-avoid-conflicts).

Dans les cas suivants, vous souhaiterez peut-être ignorer vos modifications apportées à la ressource locale. Cliquez sur **[!UICONTROL Discard Changes]**.

* Vous ne souhaitez pas enregistrer vos modifications locales dans AEM.
* Vous commencez à apporter des modifications à la ressource d’origine après avoir enregistré certaines modifications.
* Vous arrêtez de modifier la ressource car cela n’est plus nécessaire.

Si nécessaire, activez l’extraction. La ressource mise à jour est supprimée du dossier de cache local et téléchargée à nouveau lorsque vous la modifiez ou l’ouvrez.

## Charger et ajouter de nouvelles ressources dans AEM {#upload-and-add-new-assets-to-aem}

Les utilisateurs peuvent ajouter de nouvelles ressources au référentiel DAM. Par exemple, vous êtes un photographe d’agence ou un entrepreneur souhaitant ajouter au référentiel AEM un grand nombre de photos d’une séance photo. Pour ajouter du contenu neuf à AEM, cliquez sur ![Icône Upload to cloud](assets/do-not-localize/upload_to_cloud_da2.png) dans la barre supérieure de l’application. Accédez aux fichiers de ressources du système de fichiers local et cliquez sur **[!UICONTROL Select]**. L’application commence à charger la ressource et affiche une barre de progression au bas de l’écran si le chargement de la ressource prend plus de temps. N’utilisez pas d’espaces blancs ni de caractères non valides lors de la création ou du chargement de dossiers. Consultez la liste des caractères dans [Création de dossiers dans AEM Assets](https://helpx.adobe.com/fr/experience-manager/6-5/assets/using/managing-assets-touch-ui.html#Creatingfolders).

<!-- ![Download progress bar for large-sized assets](assets/upload_status_da2.png "Download progress bar for large-sized assets")
-->

Vous pouvez charger des dossiers ou des fichiers spécifiques depuis votre système de fichiers local. La hiérarchie d’un dossier est conservée lorsque ce dossier est chargé. Avant de charger des ressources en masse, reportez-vous à [Chargements en masse](#bulk-upload-assets).

Pour afficher la liste des ressources transférées au cours d’une session donnée, cliquez sur **[!UICONTROL View]** > **[!UICONTROL Assets transfers]**. La liste vous permet d’afficher et de vérifier rapidement les transferts de fichiers de la session en cours.

![Liste des ressources transférées dans une session particulière](assets/assets_transfered_da2.png "Liste des ressources transférées dans une session particulière")

>[!NOTE]
>
>La liste de transfert n’est pas persistante et n’est pas disponible si vous quittez l’application et la rouvrez.

>[!NOTE]
>
>Si le téléchargement des fichiers échoue et que vous vous connectez au déploiement d’AEM 6.5.1 ou version ultérieure, reportez-vous à ces [informations de dépannage](troubleshoot.md#upload-fails).

## Utiliser plusieurs ressources {#work-with-multiple-assets}

Les utilisateurs peuvent facilement utiliser et gérer plusieurs ressources à l’aide d’actions telles que le chargement de toutes les modifications en une seule fois ou le chargement de dossiers imbriqués en quelques clics.

### Parcourir les dossiers volumineux {#browse-large-folders}

Lorsque vous utilisez des dossiers contenant de nombreuses ressources, faites défiler l’écran pour afficher plus de ressources. Pour faire défiler l’écran à l’aide du clavier, appuyez plusieurs fois sur la touche de tabulation afin de sélectionner la ressource située en haut. La ressource sélectionnée est mise en surbrillance. Utilisez maintenant la touche fléchée Bas pour parcourir la liste des ressources.

### Actions rapides pour les ressources sélectionnées {#quick-actions-for-selected-assets}

Cliquez sur la vignette de quelques ressources pour sélectionner ces ressources. Pour sélectionner toutes les ressources, cochez la case située dans la barre supérieure de l’application. L’ensemble des actions applicables à l’ensemble des ressources sélectionnées s’affiche dans une barre d’outils au bas de l’application.

![La barre d’outils en bas affiche les actions pertinentes pour les ressources sélectionnées](assets/actions_bottom_toolbar1_da2.png "La barre d’outils en bas affiche les actions pertinentes pour les ressources sélectionnées")

![Aucune action dans la barre d’outils si aucune action commune pour la sélection](assets/actions_bottom_toolbar2_da2.png "Aucune action dans la barre d’outils si aucune action commune pour la sélection")

Les actions disponibles dans la barre d’outils située en bas dépendent du statut des fichiers sélectionnés. Par exemple, si vous ne sélectionnez que des fichiers **[!UICONTROL Edited Locally]**, une icône **[!UICONTROL Upload Changes]** s’affiche. Si vous sélectionnez une combinaison de fichiers **[!UICONTROL Edited locally]** et **[!UICONTROL Cloud only]**, l’action **[!UICONTROL Upload Changes]** n’est pas disponible.

### Rechercher toutes les images modifiées {#find-all-edited-images}

L’application fournit une vue, appelée **[!UICONTROL Edited locally]**, qui vous permet d’accéder rapidement à tous les fichiers que vous avez téléchargés localement (par le biais d’actions [!UICONTROL Open] ou [!UICONTROL Edit]) puis modifiés. L’application vous permet de sélectionner toutes les ressources modifiées localement et de charger les modifications en quelques clics. Cette vue affiche également les ressources modifiées localement qui présentent un conflit de modification.

![Filtre pour afficher toutes les ressources modifiées localement](assets/edited_locally_filter_da2.png "Filtre pour afficher toutes les ressources modifiées localement, pour le chargement en masse des modifications")

### Chargement en masse de ressources {#bulk-upload-assets}

Les utilisateurs ou les organisations, tels que les photographes ou les agences de création, peuvent créer de nombreuses ressources locales dans des scénarios, tels que des séances photo, des retouches ou une sélection à partir d’un ensemble plus grand effectué en dehors d’AEM. Ils peuvent charger ces dossiers locaux volumineux dans AEM Assets directement depuis l’appli de bureau. Les hiérarchies de dossiers sont conservées et l’ensemble des sous-dossiers imbriqués et des ressources incluses est chargé. Les ressources chargées sont immédiatement disponibles pour être utilisées par d’autres utilisateurs du même serveur. Les ressources sont chargées à l’arrière-plan et, par conséquent, l’opération n’est pas associée à une session du navigateur web.

![Chargement en masse de plusieurs dossiers locaux du bureau vers AEM](assets/upload_local_folders_da2.png "Chargement en masse de plusieurs dossiers locaux du bureau vers AEM")

Après le chargement, si les modifications attendues ne sont pas reflétées dans l’application, cliquez sur l’icône Actualiser ![Icône Actualiser](assets/do-not-localize/refresh.png).

>[!NOTE]
>
>N’utilisez pas la fonctionnalité de chargement pour migrer des ressources sur deux déploiements AEM. Consultez plutôt le [guide de migration](https://helpx.adobe.com/fr/experience-manager/6-5/assets/using/assets-migration-guide.html).

### Liste des ressources transférées {#list-of-transferred-assets}

Pour afficher la liste des ressources transférées au cours d’une session donnée, voir [Chargement de ressources dans AEM](#upload-and-add-new-assets-to-aem).

## Processus avancé : démarrez à partir de l’interface web d’AEM Assets {#adv-workflow-start-from-aem-ui}

Si nécessaire, lancez votre processus à partir de l’interface web d’AEM Assets. L’appli de bureau s’intègre à AEM pour prendre le relais lorsque nécessaire à l’aide des actions de bureau.

La découverte de ressources constitue un cas particulier de démarrage du processus à partir de l’interface web. La barre Omnisearch de l’interface utilisateur d’Assets offre une expérience de recherche riche et avancée. Vous voudrez peut-être commencer par localiser une ressource souhaitée sur le web, puis lancer le processus dans l’application, à l’aide des [!UICONTROL Desktop Actions]. Certains exemples incluent le filtrage des résultats de recherche à l’aide de facettes, la localisation d’une ressource spécifique sous licence Adobe Stock ou une personnalisation mise en œuvre par votre entreprise et autorisant une meilleure découverte à partir de l’interface web.

La fonctionnalité de l’appli de bureau est utilisée lorsque vous tentez les actions suivantes sur l’interface web d’Assets :

* Les [!UICONTROL Desktop Actions] qui autorisent les actions [!UICONTROL Open], [!UICONTROL Edit] et [!UICONTROL Reveal]
* [!UICONTROL Upload folder]
* [!UICONTROL Check-out] ou [!UICONTROL check-in]

Par exemple, les actions disponibles dans l’interface web pour une ressource extraite dans l’application sont [!UICONTROL Open], [!UICONTROL Reveal] et [!UICONTROL Check-in].

![Actions du bureau dans l’interface web d’AEM](assets/assets_web_actions_da2.png "Actions du bureau dans l’interface web d’AEM")

>[!NOTE]
>
>Le navigateur peut vous inviter à autoriser le lancement de l’appli de bureau Adobe Experience Manager. Pour bénéficier d’un transfert ininterrompu du navigateur vers l’application, cochez la case appropriée afin de toujours permettre à l’application de prendre le relais.

Les informations ou le processus suivants sont introuvables à l’aide de l’interface web. Utilisez l’appli de bureau car l’interface web ne surveille pas les modifications locales et n’est pas consciente des éléments suivants :

* Fichiers modifiés localement
* Fichiers présentant un conflit de modification et méthode de résolution de ce conflit
* Chargement des modifications locales dans AEM
* Différents statuts des fichiers disponibles localement

Au contraire, vous pouvez ouvrir la ressource dans l’interface web à partir de l’appli de bureau à l’aide de l’action **[!UICONTROL Open In Web]**.

## Processus avancé : collaborer sur les mêmes fichiers et éviter les conflits de modification {#adv-workflow-collaborate-avoid-conflicts}

Dans les environnements de collaboration, plusieurs utilisateurs peuvent travailler sur le même ensemble de ressources, ce qui peut entraîner des conflits de version. Pour prévenir les conflits, observez les bonnes pratiques suivantes :

* Ne modifiez aucune ressource en cliquant sur [!UICONTROL Open]. Ne modifiez pas les ressources téléchargées localement en les ouvrant à partir du dossier de votre système de fichiers. Les autres utilisateurs ne savent pas que ces ressources sont en cours de modification.
* Pour modifier une ressource, cliquez toujours sur [!UICONTROL Edit]. Cela ouvre la ressource dans l’application native et lui ajoute une icône de verrouillage pour indiquer aux autres utilisateurs que la ressource est en cours de modification.
* Cliquez sur [!UICONTROL Toggle Check-in] si vous avez accidentellement commencé à effectuer des modifications sans cliquer sur [!UICONTROL Edit]. Vous ajoutez ainsi une icône de verrouillage à la ressource. Si vous prévoyez de modifier une ressource ultérieurement et que vous souhaitez éviter que d’autres utilisateurs la modifient, cliquez sur [!UICONTROL Toggle Check-in] pour la verrouiller.
* Avant de modifier une ressource, vérifiez qu’elle n’est pas en train d’être modifiée par d’autres utilisateurs. Recherchez l’icône de verrouillage sur la ressource.
* Une fois les modifications terminées, téléchargez-les toutes, puis archivez la ressource.

![Statuts de la modification des conflits](assets/edits_conflicts_status_da2.png "Statuts de la modification des conflits")

Si une ressource téléchargée localement est mise à jour sur le serveur AEM, l’application affiche le statut **[!UICONTROL Modified remotely]**. Vous pouvez supprimer votre copie locale ou l’actualiser en cliquant sur [!UICONTROL Remove] ou [!UICONTROL Update], respectivement. Les liens de la boîte de dialogue vous permettent d’afficher les deux versions de la ressource.

![Options pour résoudre le conflit lorsque la ressource est modifiée à distance](assets/modified_remotely_dialog_da2.png "Options pour résoudre le conflit lorsque la ressource est modifiée à distance")

Si une ressource que vous modifiez localement est également mise à jour sur le serveur à votre insu, l’application affiche le statut **[!UICONTROL Editing Conflict]**. Vous pouvez conserver un jeu de modifications : conserver vos modifications (cliquez sur **[!UICONTROL Keep Mine]**) et supprimer celles de l’autre utilisateur, ou conserver les modifications de l’autre utilisateur et supprimer les vôtres (cliquez sur **[!UICONTROL Overwrite Mine]**).

![Options pour résoudre un conflit de modification](assets/editing_conflict_dialog_da2.png "Options pour résoudre un conflit de modification")

## Processus avancé : placer et lier des ressources dans un fichier InDesign {#adv-workflow-place-assets-indesign}

Lorsque vous utilisez l’appli de bureau AEM pour ouvrir des fichiers liés à des ressources, ces dernières sont pré-téléchargées et apparaissent placées dans les applications natives. Pour que ce processus fonctionne, votre application native doit prendre en charge le placement de liens dans des ressources locales et AEM doit prendre en charge la résolution de ces liens dans les fichiers binaires vers des références côté serveur.

L’appli de bureau AEM prend en charge ce processus avec quelques applications de bureau et formats de fichier Adobe Creative Cloud (Adobe InDesign, Adobe Illustrator et Adobe Photoshop). Le processus vous permet d’utiliser efficacement les fichiers Creative Cloud pris en charge. Ainsi, si l’utilisateur A place quelques ressources dans un fichier InDesign et les extrait dans AEM, l’utilisateur B voit ces ressources dans le fichier InDesign même si elles ne font pas partie du fichier. Les ressources sont téléchargées localement sur l’ordinateur de l’utilisateur B.

>[!NOTE]
>
>L’appli de bureau peut mapper sur n’importe quel lecteur sous Windows. Toutefois, pour un fonctionnement harmonieux, ne changez pas la lettre de lecteur par défaut. Si les utilisateurs d’une même organisation utilisent des lettres de lecteur différentes, ils ne peuvent pas voir les ressources placées par d’autres utilisateurs. Les ressources placées ne sont pas récupérées lorsque le chemin d’accès change. Les ressources placées demeurent placées dans le fichier binaire (par exemple, INDD) et ne sont pas supprimées.

Pour connaître les limites de ce processus, voir la [configuration requise et les versions prises en charge](release-notes.md#system-requirements-and-prerequisites-v2).

Pour tester ce processus avec une ressource d’image et InDesign, procédez comme suit :

1. Conservez à portée de main un fichier INDD avec des ressources placées dans AEM. Pour savoir comment créer un tel fichier INDD, voir [Placement de graphiques](https://helpx.adobe.com/fr/indesign/using/placing-graphics.html).
1. Depuis l’appli de bureau, exécutez l’action **[!UICONTROL Edit]** sur le fichier INDD avec les ressources placées dans AEM.
1. L’application télécharge à la fois le fichier InDesign et les ressources liées. Lorsque InDesign ouvre le document, les liens sont résolus et les ressources sont téléchargées et s’affichent dans le document InDesign.
1. Pour placer un nouveau graphique dans le fichier InDesign, exécutez l’action **[!UICONTROL Reveal File]** sur la ressource. L’action télécharge la ressource localement et ouvre l’emplacement du partage réseau local dans l’Explorateur Windows ou le Finder Mac.
1. Placez la ressource affichée dans le document InDesign. Un lien est alors créé dans le document.
1. Une fois les modifications effectuées dans le document InDesign, enregistrez-les et chargez-les dans AEM à l’aide de l’appli de bureau.

## Processus avancé : télécharger les ressources localement {#adv-workflow-download-assets-locally}

Dans de nombreux scénarios, l’application télécharge localement les ressources du serveur AEM sur votre système de fichiers. Les téléchargements consomment de la bande passante et de l’espace disque. Connaître ces scénarios vous permet de réduire la durée des téléchargements.

Vous téléchargez les ressources dans l’application à la demande. Voir [Téléchargement de ressources](#download-assets).

Lorsque vous utilisez l’action [!UICONTROL Open] pour ouvrir une ressource dans une application de bureau native, la ressource est téléchargée localement si elle n’est pas déjà disponible localement. Voir [Ouverture de ressources](#openondesktop-v2).

Lorsque vous affichez l’emplacement d’une ressource ou d’un dossier depuis l’application, la ressource ou le dossier est d’abord téléchargé localement, puis ouvert sur votre ordinateur dans le partage réseau local. Voir [Ouverture de ressources](#openondesktop-v2).

Lorsque vous utilisez l’action [!UICONTROL Edit] pour modifier une ressource dans une application de bureau native, la ressource est téléchargée localement si elle n’est pas déjà disponible localement. Reportez-vous à [Modification de ressources et chargement de ressources mises à jour dans AEM](#edit-assets-upload-updated-assets).

Si l’application est installée et autorisée à le faire, elle effectue les actions lorsque vous utilisez des [!UICONTROL Desktop Actions] depuis l’interface Web d’AEM. L’application télécharge d’abord la ressource, puis termine l’action.