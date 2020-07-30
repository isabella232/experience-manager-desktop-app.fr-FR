---
title: Bonnes pratiques relatives à l’appli de bureau AEM version 1.x
description: Fonctionnalités essentielles et utilisation recommandée de l’appli de bureau Adobe Experience Manager version 1.x
uuid: ba8fbc74-e1ad-4085-a031-ffd317628ba6
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 57d5cd78-abce-4ede-a50e-7c161ddb43ae
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3eb9ab89ff6338fb29cfad1a031944119908d0a2
workflow-type: tm+mt
source-wordcount: '1707'
ht-degree: 71%

---


# Bonnes pratiques relatives à l’appli de bureau AEM v1.x {#aem-desktop-app-best-practices}

## Présentation {#overview}

L’appli de bureau Adobe Experience Manager (AEM) associe votre solution de gestion des ressources numériques (DAM) à votre bureau afin que vous puissiez ouvrir les fichiers disponibles dans l’interface utilisateur web d’AEM directement sur le bureau Si vous enregistrez une ressource du bureau, celle-ci est chargée dans AEM à l’emplacement approprié.

L’appli de bureau AEM élimine les risques de mettre à jour des copies locales incorrectes ou de mettre à jour une ressource inappropriée dans AEM. Le processus convivial de l’appli de bureau est activé à l’aide de la technologie de partage réseau fournie par les systèmes d’exploitation de bureau.

L’appli de bureau monte le référentiel d’AEM Assets sous la forme d’un partage réseau sur le bureau Par conséquent, les dossiers et les fichiers s’affichent comme s’ils étaient en local. Cependant, il n’est pas recommandé d’effectuer des opérations de gestion des actifs numériques (DAM) directement sur le bureau dans le partage réseau monté du Finder ou de l’Explorateur. À la place, Adobe recommande d’utiliser l’interface utilisateur web d’AEM Assets pour effectuer des opérations, telles que la copie ou le déplacement d’un grand nombre de ressources.

>[!NOTE]
>
>Avant de lire ce document, vous pouvez consulter les [meilleures pratiques générales d’intégration d’AEM et de Creative Cloud](https://docs.adobe.com/content/help/fr-FR/experience-manager-64/assets/administer/aem-cc-integration-best-practices.html) pour un aperçu général du sujet.

## Architecture de l’appli de bureau AEM {#aem-desktop-app-architecture}

L’appli de bureau AEM utilise des partages réseau WebDAV (Windows) ou SMB (Mac) pour monter des partages réseau. Le partage réseau monté est uniquement local. L’appli de bureau AEM intercepte les appels (ouverture, lecture, écriture) et fournit une mise en cache locale supplémentaire. Elle convertit les appels distants au serveur AEM Assets en requêtes HTTP AEM optimisées. Le diagramme suivant illustre l’architecture de l’appli de bureau AEM.

![Architecture de l’appli de bureau AEM](assets/chlimage_1.png)

*Figure : architecture d’application de bureau*

La mise en cache supplémentaire à l’écriture lors de l’enregistrement d’un fichier entraîne tout d’abord l’enregistrement local du fichier (de sorte que l’utilisateur n’attend pas le transfert réseau). Ensuite, après un délai prédéfini (30 s), le fichier est chargé vers AEM en arrière-plan, puis la ressource est chargée dans AEM. L’appli de bureau AEM fournit une interface utilisateur permettant de surveiller le statut des chargements de fichiers en arrière-plan.

## Utilisation recommandée de l’appli de bureau AEM {#recommended-use-of-aem-desktop-app}

Les fonctionnalités principales de l’appli de bureau AEM incluent :

* **Ouverture de fichiers à partir de l’interface utilisateur Web AEM Assets sur le bureau**. Dans l’interface utilisateur Web, vous pouvez afficher des fichiers sur le bureau (dans le Finder, l’Explorateur) ou ouvrir un fichier à l’aide d’une application de bureau.

* **Départ et arrivée**. Les fichiers peuvent être extraits pour modification, ils sont marqués comme verrouillés pour l’utilisateur en AEM Assets. Après la modification, la ressource peut être archivée pour la déverrouiller.

* **Enregistrez les modifications apportées aux fichiers**. Toute modification que vous enregistrez dans le fichier du partage réseau est automatiquement téléchargée vers AEM et une nouvelle version est créée.

* **Placez les fichiers liés dans d’autres documents**. Dans les applications, telles que Creative Cloud ([!DNL Adobe Photoshop], [!DNL Adobe InDesign]et [!DNL Adobe Illustrator]), vous pouvez placer un fichier externe en tant que lien. Par exemple, vous pouvez placer une image dans un document d’InDesign. Dans ce cas, le montage du partage réseau vous permet de parcourir et de sélectionner des ressources d’AEM pour les placer. L’importation de fichiers liés fonctionne également dans certaines applications autres qu’Adobe telles que MS Office.

* **Résolution des références dans AEM**. Si les deux fichiers, les fichiers placés et les fichiers principaux avec lien, sont stockés dans AEM il peut fournir automatiquement des informations côté serveur sur les références de ressources.

* **Accédez au fichier à partir du bureau**. In the mounted network share, a contextual menu provides a [!UICONTROL More Info] dialog (larger preview, key metadata) and the ability to open an asset in the AEM UI.

* **Téléchargement de dossiers hiérarchiques volumineux en bloc**. Si vous utilisez l’option Créer > Téléchargement de dossiers dans l’interface utilisateur AEM pour télécharger des fichiers, AEM application de bureau télécharge la hiérarchie de dossiers sélectionnée vers l’AEM en arrière-plan. La progression du chargement peut être surveillée par une interface utilisateur dédiée dans l’appli de bureau.

## Utilisation inappropriée de l’appli de bureau AEM {#inappropriate-use-of-aem-desktop-app}

* N’utilisez pas l’appli de bureau AEM pour gérer les ressources à partir du bureau. L’appli de bureau AEM n’a pas été conçue pour remplacer les lecteurs réseau. Utilisez à la place les fonctionnalités suivantes :

   * Interface Web AEM Assets pour la gestion des ressources numériques (recherche ou partage de ressources, métadonnées, copie ou déplacement).

   * AEM desktop app [!UICONTROL Folder Upload] to upload large, hierarchical folders.

* N’utilisez pas l’appli de bureau AEM comme un client de « synchronisation du bureau » pour AEM Assets. Le principal avantage de l’appli de bureau AEM est qu’elle fournit un accès « virtuel » à l’ensemble du référentiel, et les applications de synchronisation du bureau ne synchronisent généralement que les ressources appartenant à un utilisateur. L’appli de bureau AEM fournit un certain niveau de mise en cache et de chargement en arrière-plan. Toutefois, elle fonctionne très différemment des applications de « synchronisation » typiques, telles que Adobe Creative Cloud Desktop App ou Microsoft OneDrive.

* N’utilisez pas les lecteurs réseau de l’appli de bureau AEM pour enregistrer fréquemment les ressources. Toutes les opérations d’enregistrement sont transmises à AEM Assets. Par conséquent, il n’est pas pratique d’effectuer des opérations de modification intensives directement dans le référentiel d’AEM Assets monté. La modification d’une ressource directement dans le référentiel monté écrase la chronologie de la ressource avec des versions non pertinentes et impose des surcharges supplémentaires sur le serveur.

* N’utilisez pas l’appli de bureau AEM pour faire migrer de grandes quantités de données d’une instance AEM vers une autre. Reportez-vous au [Guide de migration](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/assets/administer/assets-migration-guide.html) pour planifier et exécuter des migrations de ressources. En revanche, l’appli de bureau [prend en charge le chargement en masse](use-app-v1.md#bulkupload) d’un grand nombre de ressources pour la première fois dans [!DNL Adobe Experience Manager].

## Recommandations pour des cas d’utilisation spécifiques {#recommendations-for-selected-use-cases}

### Accès aux ressources pour les utilisateurs créatifs {#access-to-assets-for-creative-users}

L’appli de bureau AEM fournit un accès virtuel à l’ensemble du référentiel DAM, mais il peut être compliqué pour les utilisateurs créatifs de trouver et d’accéder aux ressources appropriées sur leur bureau. Utilisez les meilleures pratiques de ce document pour simplifier ce processus.

* Utilisez les fonctionnalités de collaboration de l’interface utilisateur web d’AEM Assets pour fournir aux utilisateurs créatifs un accès plus direct aux ressources appropriées. Le partage de dossiers ou de collections, la diffusion de collections dynamiques (recherches enregistrées) ou l’envoi de notifications avec des pointeurs vers les ressources appropriées sont quelques exemples de fonctionnalités de collaboration. Les utilisateurs créatifs peuvent ensuite utiliser des actions du bureau dans l’interface utilisateur web pour accéder rapidement à ces ressources sur leur bureau.

* Envisagez les autorisations appropriées pour les ressources (contrôle d&#39;accès) afin de simplifier la vue dans le référentiel DAM pour les utilisateurs créatifs, en limitant essentiellement leur accès aux seules ressources dont ils ont besoin ou qui les intéressent :

   * Certaines zones non pertinentes pour les utilisateurs créatifs peuvent être refusées pour leurs groupes d’utilisateurs, afin de les supprimer de leur vue, y compris sur le bureau.

   * La plupart des ressources de la gestion des actifs numériques sont définitives et ne sont pas destinées à être modifiées. Elles doivent être en lecture seule pour les utilisateurs créatifs.

   * Seuls les fichiers nécessitant des modifications ou des retouches doivent être activés en écriture pour les utilisateurs créatifs. Certaines organisations utilisent les projets AEM et les dossiers qu’ils créent pour héberger les ressources susceptibles d’être modifiées.

### Recherche de ressources     {#searching-assets}

Pour rechercher un fichier que vous souhaitez ouvrir sur le bureau :

* Utilisez l’interface utilisateur web d’AEM Assets pour localiser la ressource. Dans AEM Assets, non seulement la fonctionnalité de recherche est puissante (facettes de recherche, recherches enregistrées), mais elle fournit également des fonctionnalités supplémentaires permettant de trouver la ressource appropriée. Il s’agit de filtres supplémentaires, comme la possibilité de rechercher des ressources en fonction de l’état (approbation, expiration), des collections, des tâches, des notifications, et de partager des dossiers/collections avec d’autres utilisateurs/groupes.

* Une fois la ressource localisée, utilisez l’option Actions sur le Bureau de l’interface utilisateur d’AEM pour accéder à la ressource sur le          bureau.

### Mise à jour des ressources ouvertes à l’aide de l’appli de bureau AEM {#updating-assets-opened-using-aem-desktop-app}

Si vous modifiez une ressource directement à l’emplacement mappé à partir d’AEM Assets sur un partage réseau local, la ressource est transférée vers AEM chaque fois que vous l’enregistrez sur le bureau. En outre, AEM crée une version et génère des rendus.

Si une ressource stockée dans AEM nécessite une mise à jour :

* Pour les **mises à jour mineures**, telles que les demandes de retouche mineures du processus d’approbation :

   * Extrayez le fichier et ouvrez-le sur le bureau.

   * Mettez à jour le fichier.

   * Enregistrez la version mise à jour. La ressource est mise à jour et la chronologie affiche la version d’origine à des fins de comparaison..

* Pour les **mises à jour majeures**, telles qu’une demande de modification nécessitant un petit cycle créatif de travaux en cours :

   * Utilisez l’option Reveal (Afficher) pour ouvrir le dossier approprié sur le bureau..

   * Copiez le fichier dans un dossier WIP en dehors du partage de AEM Assets mappé (par exemple, copiez le fichier dans un dossier synchronisé avec l’application de bureau Adobe Creative Cloud).

   * Travaillez sur le fichier et enregistrez-le par intermittence. Les modifications ne sont pas enregistrées dans AEM Assets..

   * Une fois les modifications terminées, déplacez, copiez ou enregistrez le fichier mappé depuis AEM pour le télécharger sous une nouvelle version.

## Performances du réseau     {#network-performance}

L’expérience des utilisateurs de l’appli de bureau AEM dépend grandement d’une connectivité réseau stable et de bonne qualité entre leur bureau et le serveur AEM, ainsi que d’un serveur optimisé pour des performances élevées, en particulier lors du chargement et de la mise à jour des ressources. Ces recommandations s’appliquent aux équipes réseau/informatiques des organisations.

### Remarques relatives au réseau      {#network-considerations}

Pour connaître les meilleures pratiques concernant la configuration réseau d’AEM Assets, reportez-vous au document [Remarques relatives au réseau pour AEM Assets](https://docs.adobe.com/content/help/fr-FR/experience-manager-64/assets/administer/assets-migration-guide.html). Voici certains aspects importants permettant d’optimiser l’expérience de l’appli de bureau AEM pour les utilisateurs :

* **Utilisez un Dispatcher** correctement configuré. Utilisez AEM Dispatcher pour une sécurité supplémentaire et assurez-vous qu’il est configuré pour une connexion d’application de bureau [AEM à l’emplacement AEM derrière un répartiteur.](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher)

* **Économisez de la bande passante**. Pensez à désactiver la prévisualisation d&#39;icône dans le Finder sous Mac - lorsque vous parcourez le référentiel monté à l&#39;aide de Finder. Le Finder demande à chaque fichier de générer un aperçu et entraîne l’appli de bureau à télécharger et à mettre en cache la ressource au niveau local. Veuillez noter que, tout en économisant de la bande passante, cette opération appauvrit également l’expérience des utilisateurs travaillant sur le bureau. Elle ne doit donc être effectuée que lorsque vous travaillez avec des référentiels comportant des ressources volumineuses et/ou une bande passante limitée.

>[!NOTE]
>
>Pour désactiver les aperçus d’icônes, dans le Finder, sélectionnez View (Afficher), puis View Options (Options d’affichage) et décochez la case Show icon preview (Afficher l’aperçu des icônes). Cette opération ne fonctionne que pour le dossier actuel. Pour en faire une option par défaut, cliquez sur le bouton « Utiliser par défaut » dans la même fenêtre.

### Optimisation des performances du serveur      {#optimizing-server-performance}

To understand, how AEM Assets server should be optimized for performance, refer to [AEM Assets Performance Tuning Guide](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/assets/administer/performance-tuning-guidelines.html). Certains aspects importants relatifs aux performances du serveur pour l’appli de bureau AEM concernent l’optimisation de la configuration des processus afin d’assurer un bon fonctionnement en vue du chargement des ressources :

* **Transfert** de ressources plus performant. Configurez le modèle de processus de mise à jour des ressources [AEM pour qu’il soit transitoire](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/assets/administer/performance-tuning-guidelines.html#Workflows).

* **Limiter le processeur du serveur pour les téléchargements**. Assurez-vous que le paramètre maximal de tâches de flux de travaux parallèles est défini correctement, de sorte que les téléchargements n’épuisent pas tout le processeur.
