---
title: Meilleures pratiques et dépannage de l'application de bureau AEM
seo-title: Résolution des problèmes et bonnes pratiques concernant les applications de bureau AEM
description: Suivez les bonnes pratiques et dépassez-vous pour résoudre les problèmes occasionnels liés à l’installation, la mise à niveau, la configuration, etc.
seo-description: Suivez les bonnes pratiques et dépassez-vous pour résoudre les problèmes occasionnels liés à l’installation, la mise à niveau, la configuration, etc.
uuid: ce98a3e7-5454-41be-aaa-4252b3e0f8dd
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f5eb222a-6cdf-4ae3-9cf2-755c873f397c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a46660a3d56100e0d767e7f2b54656782bb5e7a7

---


# Troubleshoot AEM desktop app {#troubleshoot-v2}

L’application de bureau Adobe Experience Manager (AEM) se connecte à un référentiel distant de gestion des actifs numériques (DAM) du déploiement AEM. L’application récupère les informations du référentiel et les résultats de la recherche sur votre ordinateur, télécharge et télécharge les fichiers et les dossiers, et inclut des fonctionnalités de gestion des conflits avec l’interface utilisateur d’AEM Assets.

Lisez ce qui suit pour résoudre les problèmes de l’application, découvrir les meilleures pratiques et connaître les limites.

## Meilleures pratiques {#best-practices-to-prevent-troubles}

Suivez les bonnes pratiques suivantes pour éviter certains problèmes courants et le dépannage.

* **Comprendre le fonctionnement** de l’application de bureau : Avant de commencer à utiliser l’application, passez quelques minutes à connaître son fonctionnement. Connaissez la liaison entre l’interface utilisateur Web et le bureau, le mappage du référentiel, la mise en cache des ressources, l’enregistrement local et le téléchargement en arrière-plan. See [how it works](release-notes.md#how-app-works).

* **Evitez les caractères non pris en charge dans les noms** de dossier : N’utilisez pas d’espaces et de caractères non valides lors de la création ou du téléchargement de dossiers. Consultez la liste des caractères dans [Création de dossiers dans AEM Assets](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html#Creatingfolders). Certains cas d’utilisation d’AEM peuvent être affectés par des caractères non pris en charge dans le nom du dossier.

* **Meilleures pratiques pour éviter les conflits**: Pour éviter des conflits potentiels lors de la collaboration sur plusieurs ressources, voir [éviter les conflits](using.md#adv-workflow-collaborate-avoid-conflicts)de modification.

* **Utilisez le téléchargement de dossiers pour les dossiers** hiérarchiques volumineux : Au lieu d’utiliser l’interface Web Ressources ou d’autres méthodes, utilisez l’application de bureau AEM pour télécharger des dossiers volumineux. L’application télécharge les ressources en arrière-plan avec journalisation et surveillance. Voir Fichiers [de téléchargement en](using.md#bulk-upload-assets)masse.

* **Utilisez la dernière version**: Utilisez la dernière version de l’application et vérifiez toujours la compatibilité avant d’installer une nouvelle version de l’application ou avant de procéder à la mise à niveau vers une nouvelle version d’AEM. Voir les notes [de mise à jour](release-notes.md).

* **Utilisez la même lettre** de lecteur : Utilisez la même lettre de lecteur à l’échelle d’une entreprise pour mapper à la gestion des actifs numériques AEM. Pour afficher les fichiers placés par d’autres utilisateurs, les chemins d’accès doivent être identiques. L'utilisation de la même lettre de lecteur garantit un chemin constant vers les ressources DAM. Les ressources restent placées et ne sont pas supprimées même si des lettres de lecteur différentes sont utilisées par des utilisateurs différents.

* **Pensez au réseau**: Les performances réseau sont essentielles aux performances de l’application de bureau AEM. Si vous rencontrez une réponse ralentie aux transferts de fichiers ou aux opérations en masse, désactivez les fonctionnalités ou les applications susceptibles d’entraîner un trafic réseau important.

* **Cas d’utilisation non pris en charge pour l’application** de bureau : N’utilisez pas l’application pour la migration des ressources (elle nécessite une planification et d’autres outils) ; pour les opérations de gestion des actifs numériques lourdes (déplacement de grands dossiers, téléchargements volumineux, recherche de fichiers à l’aide de recherches de métadonnées avancées); et en tant que client de synchronisation (les principes de conception et les modèles d’utilisation sont différents des clients synchronisés tels que Microsoft OneDrive ou Adobe Creative Cloud Desktop Sync).

## Comment résoudre les problèmes {#troubleshooting-prep}

Pour résoudre les problèmes liés aux applications de bureau, tenez compte des informations suivantes. En outre, il vous prépare à mieux transmettre les problèmes au service à la clientèle d’Adobe si vous choisissez de demander de l’aide.

### Activer le mode de débogage {#enable-debug-mode}

Pour résoudre les problèmes, vous pouvez activer le mode de débogage et obtenir plus d’informations dans les journaux. Pour exécuter l’application en mode de débogage, utilisez les options de ligne de commande suivantes dans un terminal ou à l’invite de commande.

* Dans Windows :`SET AEM_DESKTOP_LOG_LEVEL=DEBUG & "C:\Program Files\Adobe\Adobe Experience Manager Desktop\Adobe Experience Manager Desktop.exe"`

* Sous Mac : `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`

### Emplacement des fichiers journaux {#check-log-files-v2}

Vous trouverez les fichiers journaux de l’application de bureau AEM aux emplacements suivants. Lors du téléchargement de nombreux fichiers, si le téléchargement de certains fichiers échoue, reportez-vous à la section `backend.log` Fichier à l’emplacement ci-dessus pour identifier les téléchargements ayant échoué.

* Dans Windows :`%LocalAppData%\Adobe\AssetsCompanion\Logs`

* Sous Mac : `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

>[!NOTE]
>
>Lorsque vous travaillez avec le service à la clientèle d’Adobe sur une demande d’assistance/un ticket, vous pouvez être invité à partager les fichiers journaux pour aider l’équipe d’assistance à comprendre le problème. Archivez le `Logs` dossier entier et partagez-le avec le service à la clientèle.

### Effacer le cache {#clear-cache-v2}

L’effacement du cache de l’application de bureau AEM est une tâche de dépannage préliminaire qui peut résoudre plusieurs problèmes. Effacez le cache des préférences de l’application. Voir [Définition des préférences](install-upgrade.md#set-preferences). L’emplacement par défaut du dossier cache est :

* Dans Windows :`%LocalAppData%\Adobe\AssetsCompanion\Cache\`

* Sous Mac : `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/`

Toutefois, l’emplacement peut changer en fonction du point de fin AEM configuré pour le bureau AEM. La valeur est une version codée de l’URL ciblée. For example, if the application is targeting `http://localhost:4502`, the directory name is `http%3A%2F%2Flocalhost%3A4502%2F`. Pour effacer le cache, supprimez le dossier approprié. Une autre raison de vider le cache est de libérer de l'espace disque lorsque l'espace disque est insuffisant.

>[!CAUTION]
>
>Si vous videz le cache de bureau AEM, les modifications de ressources locales qui ne sont pas synchronisées avec le serveur AEM sont irrévocablement perdues.

### Connaissance de la version de l’application de bureau AEM {#know-app-version-v2}

Cliquez sur le menu ![](assets/do-not-localize/more_options_da2.png) Application pour ouvrir le menu de l’application et cliquez sur **[!UICONTROL Help]** &gt; **[!UICONTROL About]**.

## Impossible d’afficher les fichiers importés {#placed-assets-missing}

Si vous ne pouvez pas voir les ressources que vous ou d’autres professionnels de la création avez placées dans les fichiers de support (fichiers INDD, par exemple), vérifiez les éléments suivants :

* Connexion au serveur. Une connectivité réseau défaillante peut bloquer les téléchargements de ressources.
* Taille de fichier. Le téléchargement et l’affichage des fichiers volumineux prennent plus de temps.
* Conduisez la cohérence des lettres. Si vous ou un autre collaborateur avez placé les ressources lors du mappage du DAM AEM à une autre lettre de lecteur, les ressources importées ne s’affichent pas.
* Permissions. Pour vérifier si vous êtes autorisé à récupérer les ressources importées, contactez votre administrateur AEM.

## Problèmes lors de la mise à niveau sur macOS {#issues-when-upgrading-on-macos}

Des problèmes peuvent parfois se produire lors de la mise à niveau de l’application de bureau AEM sur macOS. Cela est dû au dossier système hérité de l’application de bureau AEM qui empêche le chargement correct des nouvelles versions de l’application de bureau AEM. Pour y remédier, les dossiers et fichiers suivants peuvent être supprimés manuellement.

Avant d’exécuter les étapes suivantes, faites glisser l’ `Adobe Experience Manager Desktop` application du dossier Applications macOS vers la corbeille. Ouvrez ensuite le terminal, exécutez la commande suivante et fournissez votre mot de passe lorsque vous y êtes invité.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## Impossible de télécharger les fichiers {#upload-fails}

Si vous utilisez une application de bureau avec AEM 6.5.1 ou version ultérieure, mettez à niveau S3 ou le connecteur Azure vers la version 1.10.4 ou ultérieure. Il résout le problème d’échec de téléchargement de fichier lié à [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). Voir les instructions [d’installation](install-upgrade.md#install-v2).

## Problème de configuration SSL {#ssl-config-v2}

Les bibliothèques utilisées par l’application de bureau AEM pour la communication HTTP utilisent une application SSL stricte. Parfois, une connexion peut réussir à utiliser un navigateur, mais échoue à utiliser l’application de bureau AEM. Pour configurer SSL convenablement, installez le certificat intermédiaire manquant dans Apache. Voir [Comment installer un certificat d’autorité de certification intermédiaire dans Apache](https://access.redhat.com/solutions/43575).

## L’application ne répond pas {#unresponsive}

L’application risque rarement de ne pas répondre, d’afficher uniquement un écran blanc ou d’afficher une erreur au bas de l’interface sans aucune option dans l’interface. Procédez comme suit dans l’ordre :

1. Cliquez avec le bouton droit sur l’interface de l’application et cliquez sur **[!UICONTROL Refresh]**.
1. Quittez l’application et redémarrez-la.

Dans les deux méthodes, l’application commence au dossier DAM racine.

>[!MORELIKETHIS]
>
>* [Problèmes connus](release-notes.md#known-issues-v2)
>* [Eviter les conflits d’édition](using.md#adv-workflow-collaborate-avoid-conflicts)