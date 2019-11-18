---
title: Installation et configuration de l’application de bureau AEM
description: Installez et configurez l’application de bureau AEM pour qu’elle fonctionne avec les serveurs AEM Assets et téléchargez les ressources sur votre système de fichiers local.
uuid: 79bc9de9-5708-41f9-ac43-68c1fd2a2129
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f6365302-1690-4719-9b8c-035719422740
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 850d2c21a796599ed40164e7d6f892967563c16b

---


# Installation de l’application de bureau AEM {#install-app-v2}

## Configuration requise {#tech-specs-v2}

For detailed information, see the [AEM desktop app release notes](release-notes.md).

## Mise à niveau de l’application v1.x vers l’application v2 {#upgrade-from-previous-version}

Si vous utilisez déjà l’application, vous devez comprendre les différences et les similitudes entre la version précédente et la dernière version de l’application. Suivez également les instructions ci-dessous pour passer de la version 1.x à la dernière version.

>[!NOTE]
>
>Les applications de bureau v1.x et v2 ne peuvent pas coexister sur un ordinateur. Avant d’installer une version, désinstallez l’autre version.

Pour mettre à niveau la version 1.x vers la dernière version de l’application, suivez les instructions suivantes :

1. Avant la mise à niveau, synchronisez toutes vos ressources. Téléchargez toutes les modifications à l’aide de l’application v1.x. Cela permet d’éviter de perdre des modifications lors de la désinstallation de l’application v1.x.
1. Désinstallez l’application v1.x. Lors de la désinstallation de la version 1.x, videz le cache.
1. Redémarrez votre ordinateur.
1. Téléchargez et installez la dernière application. Suivez les instructions ci-dessous.

## Installation de la version {#install-v2}

Pour installer l’application de bureau, procédez comme suit. Désinstallez toute application de bureau existante Adobe Experience Manager v1.x avant d’installer la dernière application. Pour plus d'informations, voir ci-dessus.

1. Conservez l’URL et les informations d’identification de votre déploiement AEM à portée de main.
1. Ignorez cette étape si vous utilisez AEM 6.4.4 et versions ultérieures ou AEM 6.5.0 ou versions ultérieures. Assurez-vous que votre configuration AEM respecte les exigences de compatibilité mentionnées dans les notes de mise à jour. Si nécessaire, téléchargez le package [de](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) compatibilité approprié et installez-le à l’aide d’AEM Package Manager en tant qu’administrateur AEM. To install a package, see [How to work with Packages](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html).
1. Exécutez le fichier binaire du programme d’installation et suivez les instructions à l’écran pour l’installer.
1. Sous Windows, le programme d’installation peut demander l’installation `Visual Studio C++ Redistributable 2015`. Suivez les instructions affichées à l’écran pour l’installer. Si l’installation échoue, installez-la manuellement. Téléchargez le programme d’installation [ici](https://www.microsoft.com/en-us/download/details.aspx?id=52685) et installez les fichiers `vc_redist.x64.exe` et `vc_redist.x86.exe` . Réexécutez le programme d’installation de l’application de bureau AEM.
1. Redémarrez l’ordinateur suivant les instructions. Lancez l’application de bureau pour la configurer.
1. Pour connecter l’application à un référentiel AEM, cliquez sur l’icône de l’application dans la barre d’état pour lancer l’application. Indiquez l’adresse de l’instance AEM. Cliquez sur **[!UICONTROL Connect]** et saisissez les informations d’identification.

   ![Ecran de connexion de l’application de bureau à l’](assets/connect_da2.png "adresse du serveur d’entréeEcran de connexion à l’adresse du serveur d’entrée")

   >[!Caution]
   >
   >Vérifiez qu’il n’existe aucun espace de début ou de fin avant ou après l’adresse du serveur AEM. Sinon, l’application ne peut pas se connecter au serveur AEM.

1. Une fois la connexion établie, vous pouvez afficher la liste des dossiers et des ressources disponibles dans le dossier racine de la gestion des actifs numériques AEM. Vous pouvez parcourir les dossiers depuis l’application.

   ![Lors de la connexion, l'application affiche le](assets/firstview_da2.png "contenu de la gestion des actifs numériquesLors de la connexion, l'application affiche le contenu de la gestion des actifs numériques")

1. (AEM 6.5.1 ou version ultérieure) Si vous utilisez une application de bureau avec AEM 6.5.1 ou version ultérieure, mettez à niveau S3 ou le connecteur Azure vers la version 1.10.4 ou ultérieure. Voir Connecteur [](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AzureDataStore) Azure ou Connecteur [](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html#AmazonS3DataStore)S3.

   Si vous êtes un client Adobe Managed Services (AMS), contactez le service à la clientèle Adobe.

## Définition des préférences {#set-preferences}

Pour modifier les préférences, cliquez sur l’icône ![Options](assets/do-not-localize/more_options_da2.png) supplémentaires et sur l’icône **[!UICONTROL Preference]** ![](assets/do-not-localize/preferences_icon_da2.png)Préférences. Dans la **[!UICONTROL Preferences]** fenêtre, ajustez les valeurs des éléments suivants :

* [!UICONTROL Launch application on login].
* [!UICONTROL Show window when application starts].
* **[!UICONTROL Cache Directory]**: Emplacement du cache local de l’application (il contient les ressources téléchargées localement).
* **[!UICONTROL Network Drive Letter]**: lettre de lecteur utilisée pour mapper à la gestion des actifs numériques AEM. Ne changez pas cela si vous n'êtes pas sûr. L’application peut mapper sur n’importe quelle lettre de lecteur sous Windows. Si deux utilisateurs placent des fichiers à partir de lettres de lecteur différentes, ils ne peuvent pas voir les fichiers placés les uns par rapport aux autres. Le chemin d’accès des ressources change. Les ressources restent placées dans le fichier binaire (par exemple, INDD) et ne sont pas supprimées. L’application répertorie toutes les lettres de lecteur disponibles et utilise par défaut la dernière lettre disponible, généralement `Z`.
* **[!UICONTROL Maximum Cache Size]**: Cache autorisé sur le disque dur en Go utilisé pour stocker les ressources téléchargées localement.
* **[!UICONTROL Current cache size]**: Taille de stockage des ressources téléchargées localement. Les informations s’affichent uniquement une fois les fichiers téléchargés à l’aide de l’application.
* **[!UICONTROL Automatically download linked assets]**: Les ressources placées dans les applications Creative Cloud natives prises en charge sont automatiquement récupérées si vous téléchargez le fichier d’origine.
* **[!UICONTROL Maximum number of downloads]**: Lors du premier téléchargement de fichiers (par l’intermédiaire de l’option Afficher, Ouvrir, Modifier, Télécharger ou d’une autre option similaire), les fichiers sont téléchargés uniquement si le lot contient moins de ce nombre. La valeur par défaut est 50. Ne changez pas si vous n'êtes pas sûr. L’augmentation de la valeur peut allonger les délais d’attente et la diminution de la valeur peut ne pas vous permettre de télécharger les fichiers ou les dossiers nécessaires en une seule fois.

Pour mettre à jour les préférences indisponibles, déconnectez-vous du serveur AEM. Après avoir mis à jour les préférences, cliquez sur ![Enregistrer les préférences](assets/do-not-localize/save_preferences_da2.png) pour enregistrer les modifications.

![Préférences et](assets/preferences_da2.png "paramètres de l'application de bureau AEMPréférences de l'application de bureau")

## Désinstallation de l’application {#uninstall-the-app}

Pour désinstaller l’application sous Windows, procédez comme suit :

1. Téléchargez toutes vos modifications dans AEM pour éviter de perdre des modifications. Reportez-vous à la page [Modification des fichiers et transfert des fichiers mis à jour vers AEM](using.md#edit-assets-upload-updated-assets). Déconnectez-vous et [!UICONTROL Exit] l’application.
1. Supprimez l’application comme vous le feriez pour toute autre application du système d’exploitation. Désinstallez-le depuis Ajout et suppression de programmes sous Windows.
1. Pour supprimer le cache et les journaux, activez la case à cocher nécessaire.
   ![Boîte de dialogue de désinstallation pour supprimer les journaux et](assets/uninstall_da2.png "cacheBoîte de dialogue de désinstallation pour supprimer les journaux et le cache")
1. Suivez les instructions affichées à l’écran. Une fois terminé, redémarrez l’ordinateur.

Pour désinstaller l’application sous Mac, procédez comme suit :

1. Téléchargez toutes vos modifications dans AEM pour éviter de perdre des modifications. Reportez-vous à la page [Modification des fichiers et transfert des fichiers mis à jour vers AEM](using.md#edit-assets-upload-updated-assets). Déconnectez-vous et [!UICONTROL Exit] l’application.
1. Supprimez le `Adobe Experience Manager Desktop.app` de `/Applications`.

Pour nettoyer les caches d’application internes sous Mac et désinstaller l’application, vous pouvez également exécuter la commande suivante dans le terminal :
`/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh`
