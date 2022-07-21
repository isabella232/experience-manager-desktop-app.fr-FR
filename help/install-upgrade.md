---
title: Installation et configuration de l’appli de bureau
description: Installez et configurez l’application de bureau  [!DNL Adobe Experience Manager]  pour travailler avec les serveurs  [!DNL Adobe Experience Manager Assets] , et téléchargez les ressources sur votre système de fichiers local.
feature: Desktop App,Release Information
exl-id: 422e51c1-c456-4151-bb43-4b3d29a58187
source-git-commit: 7b884d89c34a6e45f49d4cacb0f5d537dc769742
workflow-type: ht
source-wordcount: '1411'
ht-degree: 100%

---

# Installation de l’appli de bureau [!DNL Adobe Experience Manager] {#install-app-v2}

Grâce à l’appli de bureau [!DNL Adobe Experience Manager], les ressources dans [!DNL Experience Manager] sont facilement accessibles sur votre ordinateur local et peuvent être utilisées dans n’importe quelle application de bureau. Les ressources peuvent être prévisualisées, ouvertes dans des applications de bureau natives, affichées dans le Finder de Mac ou l’Explorateur Windows pour être utilisées dans d’autres documents, et modifiées en local. Les modifications sont réenregistrées dans [!DNL Experience Manager] lors du chargement et une nouvelle version est créée dans le référentiel.

Une telle intégration permet à divers rôles de l’organisation de :

* gérer les ressources de manière centralisée dans [!DNL Experience Manager Assets] ;

* et d’accéder aux ressources dans n’importe quelle application de bureau native, y compris les applications tierces, ainsi que dans Adobe Creative Cloud. Cela permet aux utilisateurs de se conformer facilement aux différentes normes, y compris au branding.

Pour utiliser l’application de bureau [!DNL Experience Manager], procédez comme suit :

* Assurez-vous que votre version d’[!DNL Experience Manager] est prise en charge par l’appli de bureau [!DNL Experience Manager]. Consultez la [Configuration requise](release-notes.md).

* Téléchargez et installez l’application. Voir [Installation de l’application de bureau](#install-v2) ci-dessous.

* Testez la connexion à l’aide de quelques ressources. Découvrez [comment parcourir et rechercher des ressources](using.md#browse-search-preview-assets).

## Configuration requise, conditions préalables et liens de téléchargement {#tech-specs-v2}

Pour plus d’informations, voir les [[!DNL Experience Manager] Notes de mise à jour de l’appli de bureau](release-notes.md).

## Mise à niveau depuis une version antérieure {#upgrade-from-previous-version}

Si vous utilisez la version 1.x de l’application de bureau, vous devez comprendre les différences et les similitudes existant entre la version précédente et la version la plus récente. Découvrez les [nouveautés de l’application de bureau](introduction.md#whats-new-v2) et son [fonctionnement](release-notes.md#how-app-works)..

>[!NOTE]
>
>Deux versions de l’appli de bureau ne peuvent pas coexister sur le même ordinateur. Avant d’installer une version, désinstallez l’autre version.

Pour effectuer une mise à niveau à partir d’une version antérieure de l’application, suivez les instructions ci-dessous :

1. Avant de procéder à la mise à niveau, synchronisez toutes vos ressources et téléchargez vos modifications vers [!DNL Experience Manager]. Cela vous permet d’éviter la perte de modifications lors de la désinstallation de l’application.

1. Désinstallez la version précédente de l’application. Lors de la désinstallation, sélectionnez l’option permettant d’effacer le cache.

1. Redémarrez votre ordinateur.

1. [Téléchargez](release-notes.md) et [installez](#install-v2) la dernière version de l’application. Suivez les instructions ci-dessous.

## Installer {#install-v2}

Pour installer l’appli de bureau, procédez comme suit. Désinstallez toute version de l’appli de bureau [!DNL Experience Manager] Adobe v1.x avant d’installer la dernière application. Pour plus d’informations, voir ci-dessus.

1. Téléchargez la dernière version du programme d’installation à partir de la page des [notes de mise à jour](release-notes.md).

1. Conservez l’URL et les informations d’identification de votre déploiement d’[!DNL Experience Manager] à portée de main.

1. Si vous effectuez une mise à niveau à partir d’une autre version de l’application, reportez-vous à la section [Mise à niveau de l’appli de bureau](#upgrade-from-previous-version).

1. Ignorez cette étape si vous utilisez [!DNL Experience Manager] as a [!DNL Cloud Service], [!DNL Experience Manager] version 6.4.4 ou ultérieure, ou [!DNL Experience Manager] version 6.5.0 ou ultérieure. Assurez-vous que votre configuration d’[!DNL Experience Manager] respecte les exigences de compatibilité mentionnées dans les [notes de mise à jour](release-notes.md). Si nécessaire, téléchargez le [package de compatibilité](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) applicable et installez-le à l’aide du gestionnaire de modules [!DNL Experience Manager] en tant qu’administrateur [!DNL Experience Manager]. Pour installer un package, voir [Comment travailler avec des packages](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=fr).

1. Exécutez le fichier binaire du programme d’installation et suivez les instructions à l’écran pour procéder à l’installation.

1. Sous Windows, il se peut que le programme d’installation vous invite à installer `Visual Studio C++ Redistributable 2015`. Suivez les instructions affichées à l’écran pour installer ce programme. Si l’installation échoue, procédez manuellement. Téléchargez le programme d’installation [ici](https://www.microsoft.com/fr-fr/download/details.aspx?id=52685) et installez les fichiers `vc_redist.x64.exe` et `vc_redist.x86.exe`. Réexécutez le programme d’installation de l’appli de bureau [!DNL Experience Manager].

1. Redémarrez l’ordinateur conformément aux instructions. Lancez et configurez l’application de bureau.

1. Pour connecter l’application à un référentiel [!DNL Experience Manager], cliquez sur l’icône de l’application dans la barre d’état pour la lancer. Indiquez l’adresse du serveur [!DNL Experience Manager] au format `https://[aem_server]:[port]/`.

   Cliquez sur **[!UICONTROL Connect]** et saisissez les informations d’identification.

   ![Écran de connexion de l’appli de bureau pour saisir l’adresse du serveur](assets/connect_da2.png)

   *Figure : Écran de connexion pour saisir l’adresse du serveur.*

   >[!CAUTION]
   >
   >Vérifiez qu’il n’existe aucun espace avant ou après l’adresse du serveur [!DNL Experience Manager]. En effet, la présence d’un espace empêchera l’application de se connecter au serveur [!DNL Experience Manager].

1. Une fois la connexion établie, vous pouvez afficher la liste des dossiers et des ressources disponibles dans le dossier racine de la gestion des ressources numériques (DAM) [!DNL Experience Manager]. Vous pouvez parcourir les dossiers depuis l’application.

   ![Lors de la connexion, l’application affiche le contenu de la gestion des actifs numériques (DAM)](assets/firstview_da2.png)

   *Figure : L’application affiche le contenu de la gestion des actifs numériques (DAM) après la connexion*

1. ([!DNL Experience Manager] version 6.5.1 ou ultérieure) Si vous utilisez l’appli de bureau [!DNL Experience Manager] avec la version 6.5.1 ou ultérieure, mettez à niveau le connecteur Azure ou S3 vers la version 1.10.4 ou ultérieure. Voir [Connecteur Azure](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html?lang=fr#azure-data-store) ou [Connecteur S3](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/data-store-config.html?lang=fr#amazon-s-data-store).

   Si vous êtes un client d’Adobe Managed Services (AMS), contactez le Service clientèle d’Adobe.

## Définition des préférences {#set-preferences}

Pour modifier les préférences, cliquez sur ![Icône Autres options](assets/do-not-localize/more_options_da2.png) puis sur **[!UICONTROL Preference]** ![ Icône Préférences](assets/do-not-localize/preferences_icon_da2.png). Dans la fenêtre **[!UICONTROL Preferences]**, ajustez les valeurs des éléments suivants :

* [!UICONTROL Launch application on login].

* [!UICONTROL Show window when application starts].

* **[!UICONTROL Cache Directory]** : emplacement du cache local de l’application (il contient les ressources téléchargées en local).

* **[!UICONTROL Network Drive Letter]** : lettre de lecteur utilisée pour mapper l’application à la gestion des ressources numériques (DAM) [!DNL Experience Manager]. Ne changez pas cette valeur si vous n’êtes pas sûr de vous. L’application peut se mapper à n’importe quelle lettre de lecteur sous Windows. Si deux utilisateurs placent des ressources à partir de lettres de lecteur différentes, aucun ne pourra voir les ressources placées par l’autre. Le chemin d’accès des ressources change. Les ressources demeurent placées dans le fichier binaire (par exemple, INDD) et ne sont pas supprimées. L’application répertorie toutes les lettres de lecteur disponibles et utilise par défaut la dernière lettre disponible, généralement `Z`.

* **[!UICONTROL Maximum Cache Size]** : cache autorisé sur le disque dur (en Go) utilisé pour stocker les ressources téléchargées en local.

* **[!UICONTROL Current cache size]** : taille de stockage des ressources téléchargées en local. Les informations ne s’affichent qu’une fois les ressources téléchargées à l’aide de l’application.

* **[!UICONTROL Automatically download linked assets]** : les ressources placées dans les applications Creative Cloud natives prises en charge sont automatiquement récupérées si vous téléchargez le fichier d’origine.

* **[!UICONTROL Maximum number of downloads]** : ![icône d’avertissement](assets/do-not-localize/caution-icon.png) procédez à tout changement avec précaution. Lorsque vous téléchargez des ressources pour la première fois (via les options Reveal (Afficher), Open (Ouvrir), Edit (Modifier), Download (Télécharger) ou une autre option similaire), celles-ci ne sont téléchargées que si le lot contient moins de ressources que le nombre indiqué par cette valeur. La valeur par défaut est 50. Ne changez pas cette valeur si vous n’êtes pas sûr de vous. Augmenter cette valeur peut prolonger les délais d’attente et la diminuer peut vous empêcher de télécharger les ressources ou dossiers nécessaires en une seule fois.

* **[!UICONTROL Use legacy conventions when creating nodes for assets and folders]** : ![icône d’avertissement](assets/do-not-localize/caution-icon.png) procédez à tout changement avec précaution. Ce paramètre permet à l’application d’émuler le comportement de l’application v1.10 lors du chargement de dossiers. Dans la version 1.10, les noms de nœuds créés dans le référentiel respectent les espaces et la casse des noms de dossier fournis par l’utilisateur. Cependant, dans la version 2.1 de l’application, les espaces dans les noms de dossier sont convertis en tirets. Par exemple, le chargement de `New Folder` ou de `new   folder` crée le même nœud dans le référentiel si l’option n’est pas sélectionnée et si le comportement par défaut dans l’application v2.1 est conservé. Si cette option est sélectionnée, des nœuds différents sont créés dans le référentiel pour les deux dossiers ci-dessus, ce qui correspond au comportement de l’application v1.10.

   Le comportement par défaut de l’application v2.1 reste identique, c’est-à-dire qu’il remplace les espaces dans les noms de dossiers par des tirets dans le nom de nœud du référentiel et les convertit en minuscules.

* **[!UICONTROL Upload Acceleration]** : ![icône d’avertissement](assets/do-not-localize/caution-icon.png) procédez à tout changement avec précaution. Lorsque vous chargez des ressources, l’application peut réaliser ces chargements de façon simultanée de façon à en accroître la vitesse. Vous pouvez augmenter la simultanéité du chargement en déplaçant le curseur vers la droite. Le curseur situé à l’extrême gauche signifie qu’il n’y a pas de simultanéité (chargement à thread unique), tandis que la position centrale correspond à 10 threads simultanés et la limite maximale à l’extrême à 20 threads simultanés. Une limite de concurrence plus élevée est plus gourmande en ressources.

Pour mettre à jour les préférences non disponibles, déconnectez-vous du serveur [!DNL Experience Manager] puis réactualisez. Après avoir mis à jour les préférences, cliquez sur ![Save preferences](assets/do-not-localize/save_preferences_da2.png) (Enregistrer les préférences).

![Préférences et paramètres de l’appli de bureau](assets/preferences_da2.png)

*Figure : Préférences de l’appli de bureau.*

### Prise en charge des proxys {#proxy-support}

L’appli de bureau [!DNL Experience Manager] utilise le proxy prédéfini du système pour se connecter à Internet par le biais du protocole HTTPS. L’application ne peut se connecter qu’à l’aide d’un proxy réseau ne nécessitant pas d’authentification supplémentaire.

Si vous configurez ou modifiez les paramètres du serveur proxy pour Windows (Options Internet > Paramètres réseau), redémarrez l’appli de bureau [!DNL Experience Manager] afin que les modifications soient prises en compte. La configuration du proxy s’applique lorsque vous lancez l’appli de bureau. Fermez et relancez l’application pour que les modifications prennent effet.

Si votre proxy nécessite une authentification, l’équipe informatique peut autoriser l’URL d’[!DNL Experience Manager Assets] dans les paramètres du serveur proxy afin d’autoriser le trafic de l’application.

## Désinstallation de l’application {#uninstall-the-app}

Pour désinstaller l’application sous Windows, procédez comme suit :

1. Chargez toutes vos modifications dans [!DNL Experience Manager] pour éviter de perdre les modifications. Reportez-vous à [Modification de ressources et chargement de ressources mises à jour dans [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Déconnectez-vous et quittez l’application (via [!UICONTROL Exit]).

1. Supprimez l’application comme vous le feriez pour une autre application du système d’exploitation. Désinstallez-la via la fenêtre d’ajout et de suppression de programmes sous Windows.

1. Pour supprimer le cache et les journaux, cochez la case appropriée.

   ![Boîte de dialogue de désinstallation pour supprimer les journaux et le cache](assets/uninstall_da2.png)

1. Suivez les instructions s’affichant à l’écran. Lorsque vous avez terminé, redémarrez l’ordinateur.

Pour désinstaller l’application sous Mac, procédez comme suit :

1. Chargez toutes vos modifications dans [!DNL Experience Manager] pour éviter de perdre les modifications. Reportez-vous à [Modification de ressources et chargement de ressources mises à jour dans [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Déconnectez-vous et quittez l’application (via [!UICONTROL Exit]).

1. Supprimez le fichier `Adobe Experience Manager Desktop.app` du dossier `/Applications`.

Vous pouvez également, pour nettoyer les caches d’application internes sous Mac et désinstaller l’application, exécuter la commande suivante dans le terminal :

```shell
/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh
```
