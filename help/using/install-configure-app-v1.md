---
title: Installation et configuration de l’appli de bureau v1.10
description: Installez et configurez l’application de bureau [!DNL Experience Manager] version 1.10 pour qu’elle fonctionne avec les serveurs [!DNL Assets] et mappez les ressources à monter en tant que lecteur sur votre bureau.
exl-id: 7f3bdfb1-d345-4e48-b020-6e06531f46f2
source-git-commit: df5283f6bef6adbb007bf93c6dabb3b12e430f58
workflow-type: ht
source-wordcount: '910'
ht-degree: 100%

---

# Installer et configurer l’appli de bureau [!DNL Experience Manager] v1.10 {#install-and-configure-aem-desktop-app}

Grâce à l’appli de bureau [!DNL Experience Manager], les ressources d’[!DNL Experience Manager] sont facilement accessibles sur votre ordinateur local et peuvent être utilisées dans n’importe quelle application de bureau. Les ressources sont aisément affichées dans le Finder de Mac ou l’Explorateur Windows, ouvertes dans des applications de bureau et modifiées en local ; les modifications sont réenregistrées dans [!DNL Experience Manager] lors du chargement et une nouvelle version est créée dans le référentiel.

Cette intégration permet à différents rôles au sein de l’entreprise de gérer les ressources de manière centralisée dans Assets, et d’y accéder dans Creative Cloud et d’autres applications, tout en facilitant la conformité avec les diverses normes, y compris le branding.

Pour utiliser l’appli de bureau [!DNL Experience Manager],

* Assurez-vous que la version de votre serveur [!DNL Experience Manager] est prise en charge par l’appli de bureau [!DNL Experience Manager]. Voir le [tableau de compatibilité](release-notes-of-v1.md#compatibilitymatrix).

* Téléchargez et installez l’application.

* Testez la connexion à l’aide de quelques ressources. Voir [Accès aux ressources et ouverture de ces éléments sur votre ordinateur de bureau](use-app-v1.md#openondesktop).

## Configuration requise, conditions préalables et liens de téléchargement {#system-requirements-prerequisites-and-download-links}

Pour plus d’informations, voir les [[!DNL Experience Manager] Notes de mise à jour de l’appli de bureau](release-notes-of-v1.md).

## Installer et connecter l’appli au serveur [!DNL Experience Manager] {#install-and-connect-aem-desktop-app-to-aem-server}

Pour plus d’informations, voir [Installation et connexion de l’appli de bureau [!DNL Experience Manager] au serveur [!DNL Experience Manager] ](use-app-v1.md#installandconnect).

>[!NOTE]
>
>Une seule instance de l’appli de bureau [!DNL Experience Manager] peut être installée et active à la fois.

## Gestion des fichiers {#file-handling}

Lorsque vous modifiez des fichiers à partir d’un partage réseau monté par l’appli de bureau AEM, les fichiers sont enregistrés à cet emplacement en deux phases. Dans la première phase, un fichier est enregistré localement. L’utilisateur ou l’utilisatrice peut enregistrer le fichier et continuer à travailler sur ce dernier, sans attendre que le transfert soit terminé.

Dans la seconde phase, l’appli de bureau charge le fichier mis à jour sur le serveur [!DNL Experience Manager] après une période prédéfinie (par exemple, 30 s). Cette opération s’effectue en arrière-plan. Utilisez l’option View Asset Status (Afficher l’état des ressources) pour afficher l’état de l’opération de chargement.

1. Téléchargez une ressource vers Assets.

1. Cliquez/appuyez sur l’icône de l’appli de bureau [!DNL Experience Manager] dans la barre d’outils.

1. Sélectionnez l’option View Asset Status (Afficher le statut des ressources) dans le menu.

1. Dans la boîte de dialogue, examinez le statut de l’opération de chargement.

>[!NOTE]
>
>L’appli de bureau [!DNL Experience Manager] peut gérer des ressources d’une taille de 40 Go.

## Connexion à une instance [!DNL Experience Manager] derrière un Dispatcher {#connect-to-an-aem-instance-behind-a-dispatcher}

Les méthodes copy et move de l’API Assets nécessitent que les en-têtes supplémentaires suivants soient transmis à [!DNL Experience Manager] :

* X-Destination
* X-Depth
* X-Overwrite

L’appli de bureau [!DNL Experience Manager] se connecte à [!DNL Experience Manager] à l’aide d’une URL qui contient le port par défaut. Par conséquent, le paramètre `virtualhosts` dans la configuration du Dispatcher doit inclure le numéro de port par défaut. Pour plus d’informations sur la configuration de `virtualhosts`, voir [Identification des hôtes virtuels](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=fr#identifying-virtual-hosts-virtualhosts).

Pour plus d’informations sur la configuration du Dispatcher afin de transmettre ces en-têtes supplémentaires, voir [Spécification des en-têtes HTTP](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=fr#specifying-the-http-headers-to-pass-through-clientheaders).

### Prise en charge des proxys {#proxy-support}

L’appli de bureau [!DNL Experience Manager] utilise le proxy prédéfini du système pour se connecter à Internet par le biais du protocole HTTPS. L’application ne peut se connecter qu’à l’aide d’un proxy réseau ne nécessitant pas d’authentification supplémentaire.

Si vous configurez ou modifiez les paramètres du serveur proxy pour Windows (Options Internet > Paramètres réseau), redémarrez l’appli de bureau [!DNL Experience Manager] afin que les modifications soient prises en compte.

>[!NOTE]
>
>La configuration du proxy est appliquée uniquement lorsque vous démarrez l’appli de bureau. Fermez et relancez l’application pour que les modifications prennent effet.

Si votre proxy nécessite une authentification, l’équipe informatique peut autoriser l’URL d’Experience Manager Assets dans les paramètres du serveur proxy afin d’autoriser le trafic de l’application.

## Personnaliser la boîte de dialogue Asset Info (Informations sur les ressources) {#customize-the-asset-info-dialog}

Vous pouvez personnaliser la boîte de dialogue Asset Info (Informations sur les ressources) en recouvrant l’un de ces composants, ou les deux :

* La page de l’interface utilisateur Granite, située à l’adresse `/libs/dam/gui/content/assets/moreinfo`.

* Le composant `/css/javascript` HTL, situé à l’adresse `/libs/dam/gui/components/admin/moreinfo`.

Le composant qui est superposé dépend de la nature de la personnalisation. Pour modifier les composants qui s’affichent dans la boîte de dialogue Informations sur les ressources, superposez la page de l’interface utilisateur Granite. Pour modifier le contenu HTML/CSS ou JavaScript de la boîte de dialogue, recouvrez le composant HTL.

## Gestion du cache {#manage-cache}

Sous Windows, le cache se situe à l’emplacement `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\`, où il existe une version codée de l’hôte configuré dans l’appli de bureau [!DNL Experience Manager]. Par exemple, `http://localhost:4502` s’affiche comme suit : `http%3A%2F%2Flocalhost%3A4502%2F`

Sous Mac OS X, un répertoire semblable est situé à l’emplacement suivant : `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`

### Option in-app pour gérer le cache {#in-app-option-to-manage-cache}

Vous pouvez contrôler la quantité d’espace disque disponible pour la mise en cache locale. Les artefacts du serveur Assets sont mis en cache localement pour garantir une expérience plus fluide. Vous pouvez modifier les valeurs par défaut en fonction de vos besoins. Vous pouvez également vider le cache pour récupérer à nouveau toutes les ressources. Pour définir les options de votre choix, cliquez sur l’icône de l’application, puis sur **[!UICONTROL Advanced]** > **[!UICONTROL Manage Cache]**.

>[!NOTE]
>
>Lorsque vous effacez le cache, les modifications non enregistrées sont conservées. Toutes les ressources non archivées dans le serveur [!DNL Experience Manager] sont conservées.

### Modification de l’emplacement du cache sous Windows {#change-location-of-cache-on-windows}

L’emplacement par défaut du cache de l’appli de bureau [!DNL Experience Manager] est le suivant :

* Sous Windows, `%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`.

* Sous Mac, `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`.

`EncodedAEMEndpoint` est l’URL du point d’entrée d’[!DNL Experience Manager] configuré par l’application. La valeur est une version codée de l’URL de ciblage du serveur [!DNL Experience Manager]. Par exemple, si l’application cible est `http://localhost:4502`, le nom du répertoire est `http%3A%2F%2Flocalhost%3A4502`. Le chemin d’accès Windows au répertoire du cache dans cet exemple est `%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502`.

Pour faire pointer l’application vers un autre dossier ou lecteur, modifiez son fichier de configuration.

1. Accédez au répertoire d’installation de l’application. L’emplacement par défaut sous Windows est `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop`.

1. Modifiez le fichier Desktop.exe.config d’Adobe Experience Manager à l’aide d’un éditeur de texte.

   Des privilèges d’administrateur sont nécessaires pour enregistrer les modifications apportées à ce fichier.

1. Recherchez la chaîne « ProxyCacheRoot ». Comme vous pouvez le voir, sa valeur est définie sur l’emplacement du cache `%LocalAppData%\Adobe\AssetsCompanion\Cache`. Il vous suffit de définir cette valeur sur n’importe quel chemin d’accès valide.

   >[!NOTE]
   >
   >L’application crée automatiquement un sous-répertoire *&lt;Point d’entrée AEM codé>* ; ce comportement n’est pas configurable.

>[!MORELIKETHIS]
>
* [Présentation de l’appli de bureau [!DNL Experience Manager] .](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app.html?lang=fr)
* [Utilisation de l’appli de bureau [!DNL Experience Manager] .](use-app-v1.md)
* [Résolution des problèmes liés à l’appli de bureau [!DNL Experience Manager] .](troubleshoot-app-v1.md)
