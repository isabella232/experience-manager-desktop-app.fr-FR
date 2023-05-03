---
title: Bonnes pratiques relatives à l’appli de bureau v1.10
description: Fonctionnalités essentielles et utilisation recommandée de l’appli de bureau [!DNL Adobe Experience Manager] version 1.10.
exl-id: 5de06b33-c05c-47eb-b884-408b6f9afc94
source-git-commit: 7a7236c36f615e97e9d040e6139368a931eb579e
workflow-type: tm+mt
source-wordcount: '1676'
ht-degree: 86%

---

# Bonnes pratiques relatives à l’appli de bureau AEM v1.10 {#aem-desktop-app-best-practices}

## Présentation {#overview}

L’appli de bureau [!DNL Adobe Experience Manager] associe votre solution de Gestion des actifs numériques (DAM) à votre bureau afin que vous puissiez ouvrir les fichiers disponibles dans l’interface utilisateur Web d’AEM directement sur le bureau. Si vous enregistrez une ressource du bureau, celle-ci est chargée dans AEM à l’emplacement approprié.

L’appli de bureau AEM élimine les risques de mettre à jour des copies locales incorrectes ou de mettre à jour une ressource inappropriée dans AEM. Le workflow convivial de l’appli de bureau est activé à l’aide de la technologie de partage réseau fournie par les systèmes d’exploitation de bureau.

L’appli de bureau monte le référentiel d’AEM Assets sous la forme d’un partage réseau sur le bureau Par conséquent, les dossiers et les fichiers apparaissent comme s’ils étaient locaux. Toutefois, il n’est pas recommandé d’effectuer des opérations de gestion des ressources numériques directement à partir du bureau dans le partage réseau monté dans le Finder ou l’Explorateur. Adobe recommande plutôt d’utiliser l’interface utilisateur web d’AEM Assets pour effectuer des opérations, telles que copier ou déplacer un grand nombre de ressources.

>[!NOTE]
>
>Avant de lire ce document, vous pouvez consulter [Bonnes pratiques d’intégration AEM et Creative Cloud](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/aem-cc-integration-best-practices.html?lang=fr) pour un aperçu général de la rubrique.

## Architecture de l’appli de bureau AEM {#aem-desktop-app-architecture}

L’appli de bureau AEM utilise des partages réseau WebDAV (Windows) ou SMB (Mac) pour monter des partages réseau. Le partage réseau monté est uniquement local. L’appli de bureau AEM intercepte les appels (ouverture, lecture, écriture) et fournit une mise en cache locale supplémentaire. Elle convertit les appels distants au serveur AEM Assets en requêtes HTTP AEM optimisées. Le diagramme suivant illustre l’architecture de l’appli de bureau AEM.

![Architecture de l’appli de bureau AEM](assets/arch_v1.png)

*Figure : Architecture de l’appli de bureau AEM*

La mise en cache supplémentaire à l’écriture lors de l’enregistrement d’un fichier entraîne tout d’abord l’enregistrement local du fichier (de sorte que l’utilisateur n’attend pas le transfert réseau). Ensuite, après un délai prédéfini (30 s), le fichier est chargé vers AEM en arrière-plan, puis la ressource est chargée dans AEM. L’appli de bureau AEM fournit une interface utilisateur permettant de surveiller le statut des chargements de fichiers en arrière-plan.

## Utilisation recommandée de l’appli de bureau AEM {#recommended-use-of-aem-desktop-app}

Les fonctionnalités principales de l’appli de bureau AEM incluent :

* **Ouverture de fichiers à partir de l’interface utilisateur web d’AEM Assets sur le bureau**. À partir de l’interface utilisateur web, vous pouvez afficher des ressources sur le bureau (dans le Finder, l’Explorateur) ou ouvrir une ressource à l’aide d’une appli de bureau.

* **Extraction et archivage**. Les ressources peuvent être extraites pour modification et sont marquées comme verrouillées pour l’utilisateur dans AEM Assets. Après la modification, la ressource peut être archivée pour la déverrouiller.

* **Enregistrement des modifications apportées aux fichiers**. Toute modification que vous enregistrez dans le fichier du partage réseau est automatiquement chargée dans AEM et une nouvelle version est créée.

* **Placez les ressources liées dans d’autres documents**. Dans les applications, telles que Creative Cloud ([!DNL Adobe Photoshop], [!DNL Adobe InDesign] et [!DNL Adobe Illustrator]), vous pouvez placer un fichier externe en tant que lien. Par exemple, vous pouvez placer une image dans un document InDesign. Dans ce cas, le montage du partage réseau vous permet de parcourir et de sélectionner des ressources d’AEM pour les placer. L’importation de fichiers liés fonctionne également dans certaines applications autres qu’Adobe telles que MS Office.

* **Résolution des références dans AEM**. Si les fichiers placés et les fichiers principaux avec lien sont tous stockés dans AEM, ce dernier peut fournir automatiquement des informations côté serveur sur les références de ressources.

* **Accès à la ressource à partir du bureau**. Dans le partage réseau monté, un menu contextuel fournit une boîte de dialogue [!UICONTROL More Info] (aperçu plus large, métadonnées principales) et permet d’ouvrir une ressource dans l’interface utilisateur d’AEM.

* **Chargement en masse de dossiers hiérarchiques volumineux**. Si vous utilisez l’option Create > Folder Upload (Créer > Chargement de dossiers) de l’interface utilisateur d’AEM pour charger des ressources, l’appli de bureau AEM charge en arrière-plan la hiérarchie de dossiers sélectionnée dans AEM. La progression du chargement peut être surveillée par une interface utilisateur dédiée dans l’appli de bureau.

## Utilisation inappropriée de l’appli de bureau AEM {#inappropriate-use-of-aem-desktop-app}

* N’utilisez pas l’appli de bureau AEM pour gérer les ressources à partir du bureau. L’appli de bureau AEM n’a pas été conçue pour remplacer les lecteurs réseau. Utilisez à la place les fonctionnalités suivantes :

   * L’interface utilisateur web d’AEM Assets pour la gestion des actifs numériques (DAM) (recherche/partage de ressources, métadonnées, copie ou déplacement).

   * L’option [!UICONTROL Folder Upload] (Chargement de dossiers) de l’appli de bureau AEM pour charger des dossiers hiérarchiques volumineux.

* N’utilisez pas l’appli de bureau AEM comme un client de « synchronisation du bureau » pour AEM Assets. Le principal avantage de l’appli de bureau AEM est qu’elle fournit un accès « virtuel » à l’ensemble du référentiel, et les applications de synchronisation du bureau ne synchronisent généralement que les ressources appartenant à un utilisateur. L’appli de bureau AEM fournit un certain niveau de mise en cache et de chargement en arrière-plan. Toutefois, elle fonctionne très différemment des applications de « synchronisation » typiques, telles que Adobe Creative Cloud Desktop App ou Microsoft OneDrive.

* N’utilisez pas les lecteurs réseau de l’appli de bureau AEM pour enregistrer fréquemment les ressources. Toutes les opérations de sauvegarde sont transmises à AEM Assets. Par conséquent, il n’est pas pratique d’effectuer des opérations de modification intensives directement dans le référentiel AEM Assets monté. La modification d’une ressource directement dans le référentiel monté bloque la chronologie de la ressource avec des versions non pertinentes et impose des surcharges supplémentaires sur le serveur.

* N’utilisez pas l’appli de bureau AEM pour faire migrer de grandes quantités de données d’une instance AEM vers une autre. Voir le [Guide de migration](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/assets-migration-guide.html?lang=fr) pour planifier et exécuter des migrations de ressources. En revanche, l’appli de bureau [prend en charge le téléchargement massif](use-app-v1.md#bulkupload) d’un grand nombre de ressources pour la première fois dans [!DNL Adobe Experience Manager].

## Recommandations pour des cas d’utilisation spécifiques {#recommendations-for-selected-use-cases}

### Accès aux ressources pour les utilisateurs créatifs {#access-to-assets-for-creative-users}

L’appli de bureau AEM fournit un accès virtuel à l’ensemble du référentiel DAM, mais il peut être compliqué pour les utilisateurs créatifs de trouver et d’accéder aux ressources appropriées sur leur bureau. Utilisez ces bonnes pratiques pour les simplifier.

* Utilisez les fonctions de collaboration de l’interface utilisateur web d’AEM Assets pour offrir un accès plus direct aux ressources appropriées à l’utilisateur créatif. Le partage de dossiers ou de collections, la diffusion de collections dynamiques (recherches enregistrées) ou l’envoi de notifications avec des pointeurs vers les ressources appropriées sont quelques exemples de fonctionnalités de collaboration. Les utilisateurs créatifs peuvent ensuite utiliser des actions du bureau dans l’interface utilisateur web pour accéder rapidement à ces ressources sur leur bureau.

* Tenez compte des autorisations appropriées relatives aux ressources (contrôle d’accès) afin de simplifier l’affichage dans le référentiel DAM pour les utilisateurs créatifs, en limitant essentiellement leur accès aux seules ressources dont ils ont besoin.

   * Certaines zones non pertinentes pour les utilisateurs créatifs peuvent ne pas être autorisées pour leurs groupes d’utilisateurs, et supprimées de l’affichage, également sur le bureau.

   * La plupart des ressources de la gestion des actifs numériques (DAM) sont définitives et ne sont pas destinées à être modifiées. Elles doivent être en lecture seule pour les utilisateurs créatifs.

   * Seules les ressources nécessitant des modifications ou des retouches doivent être activées pour l’écriture pour les utilisateurs créatifs. Certaines organisations utilisent les projets AEM et les dossiers qu’ils créent pour héberger les ressources susceptibles d’être modifiées.

### Recherche de ressources {#searching-assets}

Pour rechercher un fichier que vous souhaitez ouvrir sur le bureau :

* Utilisez l’interface utilisateur web d’AEM Assets pour localiser la ressource. Dans AEM Assets, non seulement la fonctionnalité de recherche est puissante (facettes de recherche, recherches enregistrées), mais elle fournit également des fonctionnalités supplémentaires permettant de trouver la ressource appropriée. Il s’agit de filtres supplémentaires, comme la possibilité de rechercher des ressources en fonction de l’état (approbation, expiration), des collections, des tâches, des notifications, et de partager des dossiers/collections avec d’autres utilisateurs/groupes.

* Une fois la ressource localisée, utilisez l’option Actions sur le Bureau de l’interface utilisateur d’AEM pour accéder à la ressource sur le bureau.

### Mise à jour des ressources ouvertes à l’aide de l’appli de bureau AEM {#updating-assets-opened-using-aem-desktop-app}

Si vous modifiez une ressource directement à l’emplacement mappé d’AEM Assets à un partage réseau local, la ressource est téléchargée vers AEM chaque fois que vous l’enregistrez sur le bureau. En outre, AEM crée une version et génère des rendus.

Si une ressource stockée dans AEM doit être mise à jour :

* Pour les **mises à jour mineures**, telles que les demandes de retouche mineures du processus d’approbation :

   * Extrayez le fichier et ouvrez-le sur le bureau.

   * Mettez-le à jour.

   * Enregistrez la version mise à jour. La ressource est mise à jour et la chronologie affiche la version d’origine à des fins de comparaison.

* Pour les **mises à jour majeures**, telles qu’une demande de modification nécessitant un petit cycle créatif de travaux en cours :

   * Utilisez l’option Reveal (Afficher) pour ouvrir le dossier approprié sur le bureau.

   * Copiez le fichier dans un dossier de travail en cours en dehors du partage AEM Assets mappé (par exemple, copiez le fichier dans un dossier synchronisé avec l’appli de bureau Adobe Creative Cloud).

   * Travaillez sur le fichier et enregistrez-le par intermittence. Les modifications ne sont pas enregistrées dans AEM Assets.

   * Une fois les modifications terminées, déplacez, copiez ou enregistrez le fichier mappé à partir d’AEM pour le charger en tant que nouvelle version.

## Performances du réseau {#network-performance}

L’expérience des utilisateurs de l’appli de bureau AEM dépend grandement d’une connectivité réseau stable et de bonne qualité entre leur bureau et le serveur AEM, ainsi que d’un serveur optimisé pour des performances élevées, en particulier lors du chargement et de la mise à jour des ressources. Ces recommandations s’appliquent aux équipes réseau/informatiques des organisations.

### Remarques relatives au réseau {#network-considerations}

Pour connaître les bonnes pratiques relatives à la configuration réseau d’AEM Assets, reportez-vous à la section [Comment migrer des ressources en bloc](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/assets-migration-guide.html?lang=fr) document. Voici certains aspects importants permettant d’optimiser l’expérience de l’appli de bureau AEM pour les utilisateurs :

* **Utilisez un Dispatcher correctement configuré**. Utilisez un Dispatcher AEM pour plus de sécurité et assurez-vous qu’il est configuré pour une [connexion de l’appli de bureau AEM à AEM par l’intermédiaire d’un Dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher).

* **Économisez la bande passante**. Envisagez de désactiver l’aperçu des icônes dans le Finder sous Mac lorsque vous parcourez le référentiel monté à l’aide du Finder. Le Finder demande à chaque fichier de générer un aperçu et contraint l’appli de bureau à télécharger et à mettre en cache la ressource au niveau local. Veuillez noter que, tout en économisant de la bande passante, cette opération appauvrit également l’expérience des utilisateurs travaillant sur le bureau. Elle ne doit donc être effectuée que lorsque vous travaillez avec des référentiels comportant des ressources volumineuses et/ou une bande passante limitée.

>[!NOTE]
>
>Pour désactiver les aperçus d’icônes, dans le Finder, sélectionnez [!UICONTROL View], puis [!UICONTROL View Options] et décochez la case [!UICONTROL Show icon preview]. Cette opération ne fonctionne que pour le dossier actuel. Pour en faire une option par défaut, cliquez sur l’option [!UICONTROL Use as default] dans la même boîte de dialogue.

### Optimisation des performances du serveur {#optimizing-server-performance}

Pour savoir comment le serveur AEM Assets doit être optimisé en termes de performances, reportez-vous au [Guide d’optimisation des performances d’AEM Assets](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/performance-tuning-guidelines.html?lang=fr). Certains aspects importants relatifs aux performances du serveur pour l’appli de bureau AEM concernent l’optimisation de la configuration des workflows afin d’assurer un bon fonctionnement en vue du chargement des ressources :

* **Chargement des ressources plus performant**. Configurez le [modèle de workflow de mise à jour d’AEM Asset pour qu’il soit transitoire](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/performance-tuning-guidelines.html?lang=fr).

* **Limitez le processeur du serveur pour les chargements**. Assurez-vous que le nombre maximal de tâches de workflow parallèles est défini correctement, de sorte que les chargements ne consomment pas toutes les capacités du processeur.
