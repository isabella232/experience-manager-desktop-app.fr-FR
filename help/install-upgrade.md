---
title: Installation et configuration de l’appli de bureau AEM
description: Installez et configurez l’appli de bureau AEM pour qu’elle fonctionne avec les serveurs AEM Assets et téléchargez les ressources sur votre système de fichiers local.
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fbbb3eaea69c9153a8c36679bf2be3da0577574c

---


# Installation de l’appli de bureau AEM {#install-app-v2}

A l’aide de l’application de bureau AEM, les ressources d’AEM sont facilement accessibles sur votre bureau local et peuvent être utilisées dans n’importe quelle application de bureau. Les ressources peuvent être facilement dévoilées dans le Finder Mac ou l’Explorateur Windows, ouvertes dans les applications de bureau et modifiées localement - les modifications sont enregistrées dans AEM lorsque vous téléchargez et une nouvelle version est créée dans le référentiel.

Cette intégration permet à différents rôles au sein de l’entreprise de gérer les ressources de manière centralisée dans AEM Assets, et d’y accéder dans Creative Cloud et d’autres applications, tout en facilitant la conformité avec les diverses normes, y compris la valorisation de marque.

Pour utiliser l’appli de bureau AEM :

* Assurez-vous que la version de votre serveur AEM est prise en charge par l’appli de bureau AEM. Voir le [tableau de compatibilité](release-notes-of-v1.md#compatibilitymatrix).
* Téléchargez et installez l’application.
* Testez la connexion à l’aide de quelques ressources. Voir [Accès aux ressources et ouverture de ces éléments sur votre ordinateur de bureau](use-app-v1.md#openondesktop).

## System requirements prerequisites, and download links {#tech-specs-v2}

Pour plus d’informations, voir les [Notes de mise à jour de l’appli de bureau AEM](release-notes.md).

## Mise à niveau de l’application v1.x vers l’application v2 {#upgrade-from-previous-version}

Si vous utilisez déjà l’application, vous devez comprendre les différences et les similitudes existant entre la version précédente et la dernière version. Suivez également les instructions ci-dessous pour passer de la version 1.x à la dernière version.

>[!NOTE]
>
>Les applications de bureau v1.x et v2 ne peuvent pas coexister sur un ordinateur. Avant d’installer une version, désinstallez l’autre version.

Pour mettre la version 1.x à niveau vers la dernière version de l’application, procédez comme suit :

1. Avant la mise à niveau, synchronisez toutes vos ressources. Téléchargez toutes les modifications à l’aide de l’application v1.x. Vous éviterez ainsi de perdre des modifications lors de la désinstallation de l’application v1.x.
1. Désinstallez l’application v1.x tout en vidant le cache.
1. Redémarrez votre ordinateur.
1. Téléchargez et installez la dernière application. Suivez les instructions ci-dessous.

## Installation de la version {#install-v2}

Pour installer l’appli de bureau, procédez comme suit. Désinstallez toute instance de l’appli de bureau Adobe Experience Manager v1.x avant d’installer la dernière application. Pour plus d’informations, voir ci-dessus.

1. Conservez l’URL et les informations d’identification de votre déploiement d’AEM à portée de main.
1. Ignorez cette étape si vous utilisez AEM 6.4.4 et versions ultérieures ou AEM 6.5.0 ou versions ultérieures. Assurez-vous que votre configuration d’AEM respecte les exigences de compatibilité mentionnées dans les notes de mise à jour. Si nécessaire, téléchargez le [package de compatibilité](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) applicable et installez-le à l’aide d’AEM Package Manager en tant qu’administrateur AEM. Pour installer un package, voir [Comment travailler avec des packages](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html).
1. Exécutez le fichier binaire du programme d’installation et suivez les instructions à l’écran pour procéder à l’installation.
1. Sous Windows, il se peut que le programme d’installation vous invite à installer `Visual Studio C++ Redistributable 2015`. Suivez les instructions affichées à l’écran pour installer ce programme. Si l’installation échoue, procédez manuellement. Téléchargez le programme d’installation [ici](https://www.microsoft.com/en-us/download/details.aspx?id=52685) et installez les fichiers `vc_redist.x64.exe` et `vc_redist.x86.exe`. Réexécutez le programme d’installation de l’appli de bureau AEM.
1. Redémarrez l’ordinateur conformément aux instructions. Lancez l’appli de bureau pour la configurer.
1. Pour connecter l’application à un référentiel AEM, cliquez sur l’icône de l’application dans la barre d’état pour lancer l’application. Indiquez l’adresse de l’instance AEM. Cliquez sur **[!UICONTROL Connect]**et saisissez les informations d’identification.

   ![Écran de connexion de l’appli de bureau pour saisir l’adresse du serveur](assets/connect_da2.png "Écran de connexion de l’appli de bureau pour saisir l’adresse du serveur")

   >[!CAttention]
   >
   >Vérifiez qu’il n’existe aucun espace avant ou après l’adresse du serveur AEM. En effet, la présence d’un espace empêchera l’application de se connecter au serveur AEM.

1. Une fois la connexion établie, vous pouvez afficher la liste des dossiers et des ressources disponibles dans le dossier racine de la gestion des ressources numériques AEM. Vous pouvez parcourir les dossiers depuis l’application.

   ![À la connexion, l’appli affiche le contenu DAM](assets/firstview_da2.png "À la connexion, l’appli affiche le contenu DAM")

1. (AEM 6.5.1 ou version ultérieure) Si vous utilisez une appli de bureau avec AEM 6.5.1 ou version ultérieure, mettez à niveau le connecteur Azure ou S3 vers la version 1.10.4 ou ultérieure. Voir [Connecteur Azure](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AzureDataStore) ou [Connecteur S3](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AmazonS3DataStore).

   Si vous êtes un client d’Adobe Managed Services (AMS), contactez l’Assistance clientèle d’Adobe.

## Définition des préférences {#set-preferences}

Pour changer les préférences, cliquez sur ![Icône More options](assets/do-not-localize/more_options_da2.png) puis sur **[!UICONTROL Preference]**![Icône Preferences](assets/do-not-localize/preferences_icon_da2.png). Dans la fenêtre**[!UICONTROL Preferences]**, ajustez les valeurs des éléments suivants :

* [!UICONTROL Launch application on login].
* [!UICONTROL Show window when application starts].
* **[!UICONTROL Cache Directory]** : emplacement du cache local de l’application (il contient les ressources téléchargées localement).
* **[!UICONTROL Network Drive Letter]** : lettre de lecteur utilisée pour mapper l’application à la gestion des ressources numériques AEM. Ne changez pas cette valeur si vous n’êtes pas sûr de vous. L’application peut se mapper à n’importe quelle lettre de lecteur sous Windows. Si deux utilisateurs placent des ressources à partir de lettres de lecteur différentes, aucun ne pourra voir les ressources placées par l’autre. Le chemin d’accès des ressources change. Les ressources demeurent placées dans le fichier binaire (par exemple, INDD) et ne sont pas supprimées. L’application répertorie toutes les lettres de lecteur disponibles et utilise par défaut la dernière lettre disponible, généralement`Z`.
* **[!UICONTROL Maximum Cache Size]** : cache autorisé sur le disque dur (en Go) utilisé pour stocker les ressources téléchargées localement.
* **[!UICONTROL Current cache size]** : taille de stockage des ressources téléchargées localement. Les informations ne s’affichent qu’une fois les ressources téléchargées à l’aide de l’application.
* **[!UICONTROL Automatically download linked assets]** : les ressources placées dans les applications Creative Cloud natives prises en charge sont automatiquement récupérées si vous téléchargez le fichier d’origine.
* **[!UICONTROL Maximum number of downloads]** : lorsque vous téléchargez des ressources pour la première fois (via les options Reveal (Afficher), Open (Ouvrir), Edit (Modifier), Download (Télécharger) ou autre option similaire), celles-ci ne sont téléchargées que si le lot contient moins de ressources que le nombre indiqué par cette valeur. La valeur par défaut est 50. Ne changez pas cette valeur si vous n’êtes pas sûr de vous. Augmenter cette valeur peut prolonger les délais d’attente et la diminuer peut vous empêcher de télécharger les ressources ou dossiers nécessaires en une seule fois.

Pour mettre à jour les préférences non disponibles, déconnectez-vous du serveur AEM. Après avoir mis les préférences à jour, cliquez sur ![Save preferences](assets/do-not-localize/save_preferences_da2.png) pour les enregistrer.

![Paramètres et préférences de l’appli de bureau AEM](assets/preferences_da2.png "Préférences de l’appli de bureau")

## Désinstallation de l’application {#uninstall-the-app}

Pour désinstaller l’application sous Windows, procédez comme suit :

1. Chargez toutes vos modifications dans AEM pour éviter de perdre des modifications. Reportez-vous à [Modification de ressources et chargement de ressources mises à jour dans AEM](using.md#edit-assets-upload-updated-assets). Déconnectez-vous et quittez l’application (via [!UICONTROL Exit]).
1. Supprimez l’application comme vous le feriez pour une autre application du système d’exploitation. Désinstallez-la via la fenêtre d’ajout et de suppression de programmes sous Windows.
1. Pour supprimer le cache et les journaux, cochez la case appropriée.
   ![Boîte de dialogue de désinstallation pour supprimer les journaux et le cache](assets/uninstall_da2.png "Boîte de dialogue de désinstallation pour supprimer les journaux et le cache")
1. Suivez les instructions s’affichant à l’écran. Lorsque vous avez terminé, redémarrez l’ordinateur.

Pour désinstaller l’application sous Mac, procédez comme suit :

1. Chargez toutes vos modifications dans AEM pour éviter de perdre des modifications. Reportez-vous à [Modification de ressources et chargement de ressources mises à jour dans AEM](using.md#edit-assets-upload-updated-assets). Déconnectez-vous et quittez l’application (via [!UICONTROL Exit]).
1. Supprimez le fichier `Adobe Experience Manager Desktop.app` du dossier `/Applications`.

Vous pouvez également, pour nettoyer les caches d’application internes sous Mac et désinstaller l’application, exécuter la commande suivante dans le terminal :
`/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh`
