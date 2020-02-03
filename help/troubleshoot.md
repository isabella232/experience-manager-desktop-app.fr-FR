---
title: Meilleures pratiques et dépannage de l’application de bureau Adobe Experience Manager
description: Suivez les bonnes pratiques et les solutions de dépannage pour résoudre les problèmes occasionnels liés à l’installation, à la mise à niveau, à la configuration, etc.
uuid: ce98a3e7-5454-41be-aaaa-4252b3e0f8dd
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f5eb222a-6cdf-4ae3-9cf2-755c873f397c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ac4be2cb69a112f393ec76d5d95987634d0c9c46

---


# Troubleshoot Adobe Experience Manager desktop app {#troubleshoot-v2}

L’application de bureau Adobe Experience Manager (AEM) se connecte au référentiel de gestion des actifs numériques (DAM) d’un déploiement distant d’Experience Manager. L’appli récupère les informations du référentiel et les résultats de la recherche sur votre ordinateur, télécharge et charge les fichiers et les dossiers, et inclut des fonctionnalités de gestion des conflits avec l’interface utilisateur d’AEM Assets.

Lisez la suite de cette section pour résoudre les problèmes de l’application, découvrir les bonnes pratiques et connaître les limites.

## Bonnes pratiques {#best-practices-to-prevent-troubles}

Observez les bonnes pratiques suivantes pour éviter certains problèmes courants et relatifs au dépannage.

* **Comprendre le fonctionnement de l’appli de bureau** : avant de commencer à utiliser l’application, consacrez quelques minutes à en découvrir le fonctionnement. Sachez comment fonctionne la liaison entre l’interface utilisateur web et de bureau, le mappage de référentiel, la mise en cache de ressources, l’enregistrement en local et le chargement en arrière-plan. Voir [Fonctionnement](release-notes.md#how-app-works).

* **Éviter les caractères non pris en charge dans les noms de dossier** : n’utilisez pas d’espaces ni de caractères non valides lors de la création ou du chargement de dossiers. See a list of characters at [Create folders in Experience Manager Assets](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html#Creatingfolders). Certains cas d’utilisation d’Adobe Experience Manager peuvent être affectés par des caractères non pris en charge dans le nom du dossier.

* **Bonnes pratiques pour éviter les conflits** : pour éviter des conflits potentiels lors de la collaboration sur plusieurs ressources, voir [Éviter les conflits de modification](using.md#adv-workflow-collaborate-avoid-conflicts).

* **Utilisez le téléchargement de dossiers pour les dossiers** hiérarchiques volumineux : Au lieu d’utiliser l’interface Web Ressources ou d’autres méthodes, utilisez l’application de bureau Experience Manager pour télécharger des dossiers volumineux. L’appli charge les ressources en arrière-plan avec journalisation et surveillance. Voir [Chargement en masse de ressources](using.md#bulk-upload-assets).

* **Utilisez la dernière version**: Utilisez la dernière version de l’application et vérifiez toujours la compatibilité avant d’installer une nouvelle version de l’application ou avant de procéder à la mise à niveau vers une nouvelle version d’Adobe Experience Manager. Voir les [notes de mise à jour](release-notes.md).

* **Utilisez la même lettre** de lecteur : Utilisez la même lettre de lecteur à l’échelle d’une entreprise pour effectuer une correspondance avec la gestion des actifs numériques d’Adobe Experience Manager. Pour l’affichage des ressources placées par d’autres utilisateurs, les chemins d’accès doivent être identiques. L’utilisation de la même lettre de lecteur garantit un chemin constant vers les ressources DAM. Les ressources demeurent placées et ne sont pas supprimées même si des lettres de lecteur différentes sont utilisées par des utilisateurs différents.

* **Pensez au réseau**: Les performances réseau sont essentielles aux performances de l’application de bureau Experience Manager. Si vous obtenez une réponse ralentie aux transferts de fichiers ou aux opérations en masse, désactivez les fonctionnalités ou les applications susceptibles d’entraîner un trafic réseau important.

* **Cas d’utilisation non pris en charge pour l’appli de bureau** : n’utilisez pas l’application pour la migration des ressources (celle-ci nécessite une planification et d’autres outils) ; pour les opérations de gestion des ressources numériques lourdes (par exemple, déplacement de dossiers volumineux, chargements volumineux, recherche de fichiers à l’aide d’une recherche de métadonnées avancée) ; et en tant que client de synchronisation (les principes de conception et les modèles d’utilisation sont différents des clients synchronisés tels que Microsoft OneDrive ou Adobe Creative Cloud Desktop Sync).

* **Délai d’expiration**: Actuellement, l’application de bureau ne dispose pas d’une valeur de délai d’expiration configurable qui déconnecte la connexion entre le serveur Experience Manager et l’application de bureau après un intervalle de temps fixe. Lors du téléchargement de fichiers volumineux, si la connexion expire au bout d’un certain temps, l’application tente à nouveau de télécharger le fichier plusieurs fois en augmentant le délai d’expiration du téléchargement. Il n’existe aucun moyen recommandé de modifier les paramètres de délai d’expiration par défaut.

## Comment résoudre les problèmes {#troubleshooting-prep}

Pour résoudre les problèmes liés à l’appli de bureau, tenez compte des informations suivantes. Celles-ci vous prépareront également à mieux expliquer les problèmes à l’Assistance clientèle d’Adobe si vous choisissez de demander de l’aide.

### Activation du mode de débogage {#enable-debug-mode}

Pour résoudre les problèmes, vous pouvez activer le mode de débogage et obtenir plus d’informations dans les journaux. Pour exécuter l’application en mode de débogage, utilisez les options de ligne de commande suivantes dans un terminal ou à l’invite de commandes.

* Sous Windows :`SET AEM_DESKTOP_LOG_LEVEL=DEBUG & "C:\Program Files\Adobe\Adobe Experience Manager Desktop\Adobe Experience Manager Desktop.exe"`

* Sous Mac : `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`

### Emplacement des fichiers journaux {#check-log-files-v2}

Vous trouverez les fichiers journaux de l’appli de bureau AEM aux emplacements ci-dessous. Lors du téléchargement de nombreuses ressources, si le chargement de certains fichiers échoue, reportez-vous au fichier `backend.log` à l’emplacement ci-dessus pour identifier les chargements ayant échoué.

* Sous Windows :`%LocalAppData%\Adobe\AssetsCompanion\Logs`

* Sous Mac : `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

>[!NOTE]
>
>Lorsque vous travaillez avec l’Assistance clientèle d’Adobe sur une demande/un ticket d’assistance, vous serez peut-être invité à fournir les fichiers journaux pour aider l’équipe d’assistance à comprendre le problème. Archivez le dossier `Logs` entier et fournissez-le à l’Assistance clientèle.

### Effacer le cache {#clear-cache-v2}

L’effacement du cache de l’appli de bureau AEM est une tâche de résolution de problème préliminaire qui permet de résoudre plusieurs problèmes. Effacez le cache des préférences de l’application. Voir [Définition des préférences](install-upgrade.md#set-preferences). L’emplacement par défaut du dossier de cache est :

* Sous Windows :`%LocalAppData%\Adobe\AssetsCompanion\Cache\`

* Sous Mac : `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/`

Toutefois, l’emplacement peut varier en fonction du point de terminaison AEM configuré de l’appli de bureau AEM. La valeur est une version codée de l’URL ciblée. Par exemple, si l’application cible est `http://localhost:4502`, le nom du répertoire est `http%3A%2F%2Flocalhost%3A4502%2F`. Pour effacer le cache, supprimez le dossier approprié. Une autre raison de vider le cache est de libérer de l’espace disque lorsque l’espace disque est insuffisant.

>[!CAUTION]
>
>Si vous effacez le cache de l’appli de bureau AEM, les modifications de ressource locales qui ne sont pas synchronisées avec AEM seront définitivement perdues.

### Connaître la version de l’appli de bureau AEM {#know-app-version-v2}

Cliquez sur ![App menu](assets/do-not-localize/more_options_da2.png) pour ouvrir le menu de l’application et cliquez sur **[!UICONTROL Help]**>**[!UICONTROL About]**.

## Impossible de voir les ressources importées {#placed-assets-missing}

Si vous ne pouvez pas voir les ressources que vous ou d’autres professionnels de la création avez placées dans les fichiers de support (fichiers INDD, par exemple), vérifiez les éléments suivants :

* Connexion au serveur. Une connectivité réseau défaillante peut bloquer les téléchargements de ressources.
* Taille de fichier. Le téléchargement et l’affichage des ressources volumineuses prennent plus de temps.
* Cohérence des lettres de lecteur. Si vous ou un autre collaborateur avez placé les ressources tout en mappant le DAM AEM sur une autre lettre de lecteur, les ressources placées ne s’affichent pas.
* Permissions. Pour vérifier que vous êtes autorisé à récupérer les ressources placées, contactez votre administrateur AEM.

## Problèmes lors de la mise à niveau sous MacOS {#issues-when-upgrading-on-macos}

Des problèmes peuvent parfois survenir lors de la mise à niveau de l’appli de bureau AEM sous macOS. Cela est dû au dossier système hérité de l’appli de bureau AEM, qui empêche le chargement correct des nouvelles versions de l’application. Pour y remédier, les dossiers et fichiers suivants peuvent être supprimés manuellement.

Avant d’exécuter les étapes suivantes, faites glisser l’application `Adobe Experience Manager Desktop` du dossier des applications MacOS vers la corbeille. Ouvrez ensuite le terminal, exécutez la commande suivante et saisissez votre mot de passe lorsque vous y êtes invité.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## Chargement des fichiers impossible {#upload-fails}

Si vous utilisez une appli de bureau avec AEM 6.5.1 ou version ultérieure, mettez à niveau S3 ou le connecteur Azure vers la version 1.10.4 ou ultérieure. Cela aura pour effet de résoudre le problème d’échec de chargement de fichier lié à [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). Voir [Instructions d’installation](install-upgrade.md#install-v2).

## Problème de configuration SSL {#ssl-config-v2}

Les bibliothèques utilisées par l’appli de bureau AEM pour les communications HTTP appliquent le protocole SSL de manière stricte. Parfois, une connexion peut réussir en utilisant un navigateur, mais échouer avec l’appli de bureau AEM. Pour configurer SSL convenablement, installez le certificat intermédiaire manquant dans Apache. Voir [Comment installer un certificat d’autorité de certification intermédiaire dans Apache](https://access.redhat.com/solutions/43575).

## L’application ne répond pas {#unresponsive}

L’application risque rarement de ne plus répondre, d’afficher uniquement un écran blanc ou d’afficher une erreur au bas de l’interface sans aucune option. Procédez comme suit dans l’ordre :

1. Cliquez avec le bouton droit sur l’interface de l’application et cliquez sur **[!UICONTROL Refresh]**.
1. Quittez l’application et redémarrez-la.

Dans les deux méthodes, l’application démarre au dossier DAM racine.

>[!MORELIKETHIS]
>
>* [Problèmes connus](release-notes.md#known-issues-v2)
>* [Éviter les conflits de modification](using.md#adv-workflow-collaborate-avoid-conflicts)