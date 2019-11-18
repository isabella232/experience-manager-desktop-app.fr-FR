---
title: Meilleures pratiques concernant l'application de bureau AEM version 1.x
description: Fonctionnalités clés et utilisation recommandée de l’application de bureau Adobe Experience Manager version 1.x.
uuid: ba8fbc74-e1ad-4085-a031-ffd317628ba6
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: 57d5cd78-abce-4ede-a50e-7c161ddb43ae
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 850d2c21a796599ed40164e7d6f892967563c16b

---


# Meilleures pratiques de l'application de bureau AEM v1.x {#aem-desktop-app-best-practices}

## Présentation {#overview}

L’application de bureau Adobe Experience Manager (AEM) associe votre solution Digital Asset Management (DAM) à votre bureau afin que vous puissiez ouvrir les fichiers disponibles dans l’interface utilisateur Web d’AEM directement sur le bureau. Si vous enregistrez un fichier du bureau, il est téléchargé vers AEM à l’emplacement approprié.

L’application de bureau AEM élimine les risques de mise à jour de copies locales incorrectes ou de mise à jour d’une ressource incorrecte dans AEM. Le workflow convivial de l’application de bureau est activé à l’aide de la technologie de partage réseau fournie par les systèmes d’exploitation de bureau.

L’application de bureau monte le référentiel AEM Assets en tant que partage réseau sur le bureau. Par conséquent, les dossiers et les fichiers s’affichent comme s’ils étaient en local. Cependant, il n’est pas recommandé d’effectuer des opérations de gestion des actifs numériques (DAM) directement sur le bureau dans le partage réseau monté du Finder ou de l’Explorateur. À la place, Adobe recommande d’utiliser l’interface utilisateur web d’AEM Assets pour effectuer des opérations, telles que la copie ou le déplacement d’un grand nombre de ressources.

>[!NOTE]
>
>Avant de lire ce document, vous pouvez consulter les [meilleures pratiques générales d’intégration d’AEM et de Creative Cloud](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/aem-cc-integration-best-practices.html) pour un aperçu général du sujet.

## AEM desktop app architecture {#aem-desktop-app-architecture}

L’application de bureau AEM utilise des partages réseau WebDAV (Windows) ou SMB (Mac) pour monter des partages réseau. Le partage réseau monté est uniquement local. L’application de bureau AEM intercepte les appels (open, read, write) et fournit une mise en cache locale supplémentaire. Il convertit les appels distants au serveur AEM Assets afin d’optimiser les requêtes HTTP d’AEM. Le diagramme suivant illustre l’architecture de l’application de bureau AEM.

![Architecture des applications de bureau AEM](assets/chlimage_1.png)

La mise en cache supplémentaire à l’écriture lors de l’enregistrement d’un fichier entraîne tout d’abord l’enregistrement local du fichier (de sorte que l’utilisateur n’attend pas le transfert réseau). Ensuite, après un délai prédéfini ( 30 s), le fichier est transféré vers AEM en arrière-plan, puis la ressource est chargée dans AEM. L’application de bureau AEM fournit une interface utilisateur pour surveiller l’état des téléchargements de fichiers en arrière-plan.

## Recommended use of AEM desktop app {#recommended-use-of-aem-desktop-app}

Les principales fonctionnalités de l'application de bureau AEM sont les suivantes :

* Ouverture de fichiers à partir de l’interface utilisateur Web d’AEM Assets sur le bureau : Dans l’interface utilisateur Web, vous pouvez afficher des fichiers sur le bureau (dans le Finder, l’Explorateur) ou ouvrir un fichier à l’aide d’une application de bureau.
* Extraction et archivage : les ressources peuvent être extraites pour modification, elles sont marquées comme verrouillées pour l’utilisateur dans AEM Assets. Après la modification, la ressource peut être archivée pour la déverrouiller.
* Enregistrement des modifications apportées aux fichiers : toute modification que vous enregistrez dans le fichier du partage réseau est automatiquement chargée dans AEM et une nouvelle version est créée.
* Placez des fichiers liés dans d’autres documents : Dans des applications telles que Creative Cloud (PS, ID, AI, etc.), vous pouvez placer un fichier externe sous forme de lien (vous pouvez, par exemple, importer une image dans un document InDesign). Dans ce cas, le montage du partage réseau vous permet de parcourir et de sélectionner des fichiers d’AEM pour les placer. L’importation de fichiers liés fonctionne également dans certaines applications autres qu’Adobe telles que MS Office.
* Résolution des références dans AEM : Si le ou les fichiers importés et le ou les fichiers principaux avec des liens sont stockés dans AEM, il peut fournir automatiquement des informations côté serveur sur les références de ressources.
* Accédez au fichier à partir du bureau : Dans le partage réseau monté, un menu contextuel fournit une boîte de dialogue Plus d’informations (aperçu plus volumineux, métadonnées clés) et la possibilité d’ouvrir un fichier dans l’interface utilisateur d’AEM.
* Téléchargement de dossiers hiérarchiques volumineux en bloc : Si vous utilisez l’option Créer &gt; Télécharger les dossiers dans l’interface utilisateur d’AEM pour télécharger des fichiers, l’application de bureau AEM télécharge la hiérarchie de dossiers sélectionnée vers AEM en arrière-plan. La progression du chargement peut être surveillée par une interface utilisateur dédiée dans l’application de bureau.

## Inappropriate use of AEM desktop app {#inappropriate-use-of-aem-desktop-app}

* N’utilisez pas l’application de bureau AEM pour gérer les fichiers à partir du bureau. L'application de bureau AEM n'a pas été créée en tant que remplacement des lecteurs réseau. Utilisez à la place les fonctionnalités suivantes :
   * Interface utilisateur Web d’AEM Assets pour la gestion des ressources numériques (recherche/partage de ressources, métadonnées, copie/déplacement, etc.)
   * Téléchargement des dossiers d’application de bureau AEM pour télécharger des dossiers hiérarchiques volumineux

* Ne traitez pas l’application de bureau AEM comme un client de synchronisation de bureau pour AEM Assets. L'avantage principal de l'application de bureau AEM ici est qu'elle fournit un accès "virtuel" à l'ensemble du référentiel et que les applications de synchronisation de bureau synchronisent généralement uniquement les ressources appartenant à un utilisateur. L’application de bureau AEM fournit un certain niveau de mise en cache et de téléchargement en arrière-plan ; toutefois, il fonctionne très différemment des applications de synchronisation standard, telles que l’application de bureau Adobe Creative Cloud ou Microsoft OneDrive.
* N’utilisez pas les lecteurs de réseau d’applications de bureau AEM pour enregistrer fréquemment des ressources. Toutes les opérations d’enregistrement sont transmises à AEM Assets. Par conséquent, il n’est pas pratique d’effectuer des opérations de modification intensives directement dans le référentiel d’AEM Assets monté. La modification d’une ressource directement dans le référentiel monté écrase la chronologie de la ressource avec des versions non pertinentes et impose des surcharges supplémentaires sur le serveur.
* N’utilisez pas l’application de bureau AEM pour la migration de grandes quantités de données d’une instance AEM vers une autre. Reportez-vous au [Guide de migration](https://helpx.adobe.com/experience-manager/6-4/assets/using/assets-migration-guide.html) pour planifier et exécuter des migrations de ressources. In contrast, desktop app [supports bulk uploading](use-app-v1.md#bulkupload) large number of assets for the first time in AEM.

## Recommandations pour des cas d’utilisation spécifiques {#recommendations-for-selected-use-cases}

### Accès aux ressources pour les utilisateurs créatifs {#access-to-assets-for-creative-users}

L’application de bureau AEM fournit un accès virtuel à l’ensemble du référentiel DAM. Il peut s’avérer compliqué pour les utilisateurs créatifs de bureau de trouver et d’accéder aux ressources appropriées sur leur bureau. Utilisez les meilleures pratiques de ce document pour simplifier ce processus.

* Utilisez les fonctionnalités de collaboration de l’interface utilisateur web d’AEM Assets pour fournir aux utilisateurs créatifs un accès plus direct aux ressources appropriées. Le partage de dossiers ou de collections, la diffusion de collections dynamiques (recherches enregistrées) ou l’envoi de notifications avec des pointeurs vers les ressources appropriées sont quelques exemples de fonctionnalités de collaboration. Les utilisateurs créatifs peuvent ensuite utiliser des actions du bureau dans l’interface utilisateur web pour accéder rapidement à ces ressources sur leur bureau.
* Tenez compte des autorisations appropriées relatives aux ressources (contrôle d’accès) afin de simplifier l’affichage dans le référentiel DAM pour les utilisateurs créatifs, en limitant essentiellement leur accès aux seules ressources dont ils ont besoin :

   * Certaines zones non pertinentes pour les utilisateurs créatifs peuvent ne pas être autorisées pour leur(s) groupe(s) d’utilisateurs, et supprimées de l’affichage, également sur le bureau
   * La plupart des ressources de la gestion des actifs numériques sont définitives et ne sont pas destinées à être modifiées. Elles doivent être en lecture seule pour les utilisateurs créatifs.
   * Seules les ressources nécessitant des modifications/retouches doivent être activées pour l’écriture pour les utilisateurs créatifs. Certaines organisations utilisent les projets AEM et les dossiers qu’ils créent pour héberger les ressources susceptibles d’être modifiées.

### Recherche de ressources {#searching-assets}

Pour rechercher un fichier à ouvrir sur le bureau :

* Utilisez l’interface utilisateur web d’AEM Assets pour localiser la ressource. La recherche dans les ressources AEM est non seulement puissante (facettes de recherche, recherches enregistrées), mais elle offre également des fonctionnalités supplémentaires pour trouver la ressource appropriée. Il s’agit de filtres supplémentaires, comme la possibilité de rechercher des ressources en fonction de l’état (approbation, expiration), des collections, des tâches, des notifications, et de partager des dossiers/collections avec d’autres utilisateurs/groupes.
* Une fois la ressource localisée, utilisez l’option Actions sur le Bureau de l’interface utilisateur d’AEM pour accéder à la ressource sur le   bureau .

### Updating assets opened using AEM desktop app {#updating-assets-opened-using-aem-desktop-app}

Si vous modifiez une ressource directement à l’emplacement mappé à partir d’AEM Assets sur un partage réseau local, la ressource est transférée vers AEM chaque fois que vous l’enregistrez sur le bureau. En outre, AEM crée une version et génère des rendus.

Si une ressource stockée dans AEM nécessite une mise à jour :

* For **minor updates**, such as minor retouching requests in the approval process:

   * Extrayez le fichier et ouvrez-le sur le bureau.
   * Mettez-le à jour.
   * Enregistrez la version mise à jour. La ressource est mise à jour et la chronologie affiche la version d’origine à des fins de comparaison.

* For **major updates**, such as a change request that requires a small creative WIP cycle:

   * Utilisez l’option Afficher pour ouvrir le dossier approprié sur le bureau.
   * Copiez le fichier dans un dossier WIP en dehors du partage AEM Assets mappé (par exemple, copiez le fichier dans un dossier synchronisé avec l’application de bureau Adobe Creative Cloud).
   * Travaillez sur le fichier et enregistrez-le par intermittence. Les modifications ne sont pas enregistrées dans AEM Assets.
   * Une fois les modifications terminées, déplacez, copiez ou enregistrez le fichier mappé à partir d’AEM pour le charger en tant que nouvelle version.

## Performances du réseau {#network-performance}

La bonne expérience des utilisateurs qui utilisent l’application de bureau AEM dépend grandement d’une bonne connectivité réseau stable entre leurs ordinateurs de bureau et le serveur AEM, ainsi que du serveur configuré pour de bonnes performances, notamment en ce qui concerne le transfert et la mise à jour des ressources. Ces recommandations s’appliquent aux équipes réseau/informatiques des organisations.

### Remarques relatives au réseau {#network-considerations}

Pour connaître les meilleures pratiques concernant la configuration réseau d’AEM Assets, reportez-vous au document [Remarques relatives au réseau pour AEM Assets](https://helpx.adobe.com/experience-manager/6-4/assets/using/assets-network-considerations.html). Voici quelques-uns des aspects importants qui aident à optimiser l’expérience des utilisateurs de l’application de bureau AEM :

* **** Utiliser le répartiteur correctement configuré : Utilisez le répartiteur AEM pour une sécurité supplémentaire et assurez-vous qu’il est configuré pour la connexion de l’application de bureau [AEM à AEM derrière un répartiteur](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html#ConnectingtoAEMBehindaDispatcher)

* **Économisez la bande passante :** envisagez de désactiver l’aperçu des icônes dans le Finder sous Mac lorsque vous parcourez le référentiel monté à l’aide du Finder. Le Finder demande à chaque fichier de générer un aperçu et entraîne l’application de bureau à télécharger et à mettre en cache la ressource au niveau local. Veuillez noter que, tout en économisant de la bande passante, cette opération appauvrit également l’expérience des utilisateurs travaillant sur le bureau. Elle ne doit donc être effectuée que lorsque vous travaillez avec des référentiels comportant des ressources volumineuses et/ou une bande passante limitée.

**** Remarque : Pour désactiver l’aperçu des icônes, dans le Finder, accédez à Affichage, sélectionnez Options d’affichage, puis désélectionnez l’option "Afficher l’aperçu de l’icône". Cette opération ne fonctionne que pour le dossier actuel. Pour en faire une option par défaut, cliquez sur le bouton « Utiliser par défaut » dans la même fenêtre.

### Optimisation des performances du serveur {#optimizing-server-performance}

Pour savoir comment le serveur AEM Assets doit être optimisé en termes de performances, reportez-vous au [Guide d’optimisation des performances d’AEM Assets](https://helpx.adobe.com/in/experience-manager/6-4/assets/using/performance-tuning-guidelines.html). Certains des aspects importants des performances du serveur pour l’application AEM Desktop concernent l’optimisation de la configuration du flux de travaux afin qu’il fonctionne correctement pour les téléchargements de ressources :

* **** Transfert de fichiers plus performant : Configurez le modèle de flux de travaux [AEM Asset Update pour qu’il soit transitoire](https://helpx.adobe.com/experience-manager/6-4/assets/using/performance-tuning-guidelines.html#Workflows).

* **** Limiter le processeur du serveur pour les téléchargements : Assurez-vous que le paramètre de tâches de flux de travail parallèle maximum est défini correctement, de sorte que les téléchargements n’épuisent pas tout le processeur.