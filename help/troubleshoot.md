---
title: Bonnes pratiques et résolution des problèmes liés à l’appli de bureau Adobe Experience Manager
description: Suivez les bonnes pratiques et les solutions de dépannage pour résoudre les problèmes occasionnels liés à l’installation, à la mise à niveau, à la configuration, etc.
uuid: ce98a3e7-5454-41be-aaaa-4252b3e0f8dd
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.5/ASSETS, SG_EXPERIENCEMANAGER/6.4/ASSETS, SG_EXPERIENCEMANAGER/6.3/ASSETS
discoiquuid: f5eb222a-6cdf-4ae3-9cf2-755c873f397c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 540821ad10f14ad855c66a2b93d356ba118515c7
workflow-type: tm+mt
source-wordcount: '2230'
ht-degree: 44%

---


# Résolution des problèmes liés à l’appli de bureau Adobe Experience Manager {#troubleshoot-v2}

L’appli de bureau Adobe Experience Manager (AEM) se connecte à un référentiel de gestion des ressources numériques (DAM) d’un déploiement Experience Manager distant. L’appli récupère les informations du référentiel et les résultats de la recherche sur votre ordinateur, télécharge et charge les fichiers et les dossiers, et inclut des fonctionnalités de gestion des conflits avec l’interface utilisateur d’AEM Assets.

Lisez la suite de cette section pour résoudre les problèmes de l’application, découvrir les bonnes pratiques et connaître les limites.

## Bonnes pratiques {#best-practices-to-prevent-troubles}

Observez les bonnes pratiques suivantes pour éviter certains problèmes courants et relatifs au dépannage.

* **Comprendre le fonctionnement de l’appli de bureau** : avant de commencer à utiliser l’application, consacrez quelques minutes à en découvrir le fonctionnement. Découvrez comment fonctionne la liaison entre l’interface utilisateur web et de bureau Experience Manager, le mappage de référentiel, la mise en cache de ressources, l’enregistrement en local ainsi que le chargement en arrière-plan. Voir [Fonctionnement](release-notes.md#how-app-works).

* **Éviter les caractères non pris en charge dans les noms de dossier** : n’utilisez pas d’espaces ni de caractères non valides lors de la création ou du chargement de dossiers. Consultez la liste des caractères dans [Création de dossiers dans Experience Manager Assets](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/assets/managing/managing-assets-touch-ui.html#Creatingfolders). Certains cas d’utilisation d’Adobe Experience Manager peuvent être affectés par la présence de caractères non pris en charge dans le nom du dossier.

* **Bonnes pratiques pour éviter les conflits** : pour éviter les éventuels conflits lors de la collaboration sur plusieurs ressources, voir [Éviter les conflits de modification](using.md#adv-workflow-collaborate-avoid-conflicts).

* **Utiliser le chargement de dossiers pour les dossiers hiérarchiques volumineux** : au lieu d’utiliser l’interface web d’Assets ou d’autres méthodes, utilisez l’appli de bureau Experience Manager pour charger les dossiers volumineux. L’appli charge les ressources en arrière-plan avec journalisation et surveillance. Voir [Chargement en masse de ressources](using.md#bulk-upload-assets).

* **Utiliser la dernière version** : utilisez la dernière version de l’application et vérifiez toujours la compatibilité avant d’installer une nouvelle version de l’application ou de procéder à une mise à niveau vers une nouvelle version d’Adobe Experience Manager. Voir les [notes de mise à jour](release-notes.md).

* **Utiliser la même lettre de lecteur** : utilisez la même lettre de lecteur dans toute l’entreprise pour procéder à un mappage sur le DAM Adobe Experience Manager. Pour l’affichage des ressources placées par d’autres utilisateurs, les chemins d’accès doivent être identiques. L’utilisation de la même lettre de lecteur garantit un chemin constant vers les ressources DAM. Les ressources demeurent placées et ne sont pas supprimées même si des lettres de lecteur différentes sont utilisées par des utilisateurs différents.

* **Penser au réseau** : les performances réseau sont essentielles aux performances de l’appli de bureau Experience Manager. Si vous obtenez une réponse ralentie aux transferts de fichiers ou aux opérations en masse, désactivez les fonctionnalités ou les applications susceptibles d’entraîner un trafic réseau important.

* **Cas d’utilisation non pris en charge pour l’appli de bureau** : n’utilisez pas l’application pour la migration des ressources (celle-ci nécessite une planification et d’autres outils) ; pour les opérations de gestion des ressources numériques lourdes (par exemple, déplacement de dossiers volumineux, chargements volumineux, recherche de fichiers à l’aide d’une recherche de métadonnées avancée) ; et en tant que client de synchronisation (les principes de conception et les modèles d’utilisation sont différents des clients synchronisés tels que Microsoft OneDrive ou Adobe Creative Cloud Desktop Sync).

* **Délai d’expiration** : actuellement, l’appli de bureau ne dispose pas d’une valeur de délai d’expiration configurable qui déconnecte l’appli de bureau du serveur Experience Manager après un temps donné. Lors du chargement de ressources volumineuses, si la connexion expire au bout d’un certain temps, l’application tente à nouveau de charger la ressource plusieurs fois en augmentant le délai d’expiration du chargement. Il n’existe aucun moyen recommandé de modifier les paramètres de délai d’expiration par défaut.

## Comment résoudre les problèmes {#troubleshooting-prep}

Pour résoudre les problèmes liés à l’appli de bureau, tenez compte des informations suivantes. Celles-ci vous prépareront également à mieux expliquer les problèmes à l’Assistance clientèle d’Adobe si vous choisissez de demander de l’aide.

### Emplacement des fichiers journaux {#check-log-files-v2}

[!DNL Experience Manager] l’application de bureau stocke ses fichiers journaux aux emplacements suivants en fonction du système d’exploitation :

Sous Windows :`%LocalAppData%\Adobe\AssetsCompanion\Logs`

Sous Mac : `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

Lorsque de nombreuses ressources sont chargées, si le chargement de certains fichiers échoue, reportez-vous au fichier `backend.log` pour identifier les chargements ayant échoué.

>[!NOTE]
>
>Lorsque vous travaillez avec le service à la clientèle d’Adobe sur une demande d’assistance ou un ticket, vous pouvez être invité à partager les fichiers journaux pour aider l’équipe d’assistance clientèle à comprendre le problème. Archivez le dossier `Logs` entier et fournissez-le au représentant de l’Assistance clientèle.

### Modification du niveau de détails dans les fichiers journaux {#level-of-details-in-log}

Pour modifier le niveau des détails dans les fichiers journaux :

1. Assurez-vous que l’application n’est pas en cours d’exécution.

1. Sur le système Windows :

   1. Ouvrez une fenêtre de commande.

   1. Lancez [!DNL Adobe Experience Manager] une application de bureau en exécutant la commande :

   ```shell
   set AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe
   ```

   Sur le système Mac :

   1. Ouvrez une fenêtre de terminal.

   1. Lancez [!DNL Adobe Experience Manager] une application de bureau en exécutant la commande :

   ```shell
   AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app
   ```

Les niveaux de journal valides sont DEBUG, INFO, WARN ou ERROR. La véracité des journaux est la plus élevée dans DEBUG et la plus basse dans ERROR.

### Activation du mode de débogage {#enable-debug-mode}

Pour résoudre les problèmes, vous pouvez activer le mode de débogage et obtenir plus d’informations dans les journaux.

>[!NOTE]
>
>Les niveaux de journal valides sont DEBUG, INFO, WARN ou ERROR. La véracité des journaux est la plus élevée dans DEBUG et la plus basse dans ERROR.

Pour utiliser l’application en mode de débogage sous Mac :

1. Ouvrez une fenêtre de terminal ou une invite de commande.

1. Lancez l’application [!DNL Experience Manager] de bureau en exécutant la commande suivante :

   `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`.

Pour activer le mode de débogage sous Windows :

1. Ouvrez une fenêtre de commande.

1. Lancez [!DNL Experience Manager] une application de bureau en exécutant la commande suivante :

`AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe`.

### Effacer le cache {#clear-cache-v2}

Exécutez les étapes suivantes :

1. Début de l’application et connexion à l’instance AEM.

1. Ouvrez les préférences de l&#39;application en cliquant sur les ellipses dans le coin supérieur droit et en sélectionnant [!UICONTROL Preferences].

1. Localisez l’entrée affichant le [!UICONTROL Current Cache Size]. Cliquez sur l’icône de la corbeille en regard de cet élément.

Pour effacer manuellement le cache, procédez comme suit.

>[!CAUTION]
>
>Il s&#39;agit d&#39;une opération potentiellement destructrice. Si des modifications de fichiers locaux ne sont pas téléchargées vers [!DNL Adobe Experience Manager], ces modifications seront perdues en cours de traitement.

Le cache est effacé en supprimant le répertoire du cache de l&#39;application, qui se trouve dans les préférences de l&#39;application.

1. Démarrez l’application.

1. Ouvrez les préférences de l&#39;application en sélectionnant les ellipses dans le coin supérieur droit et en sélectionnant [!UICONTROL Preferences].

1. Notez la [!UICONTROL Cache Directory] valeur.

   Dans ce répertoire, il existe des sous-répertoires nommés d’après les [!DNL Adobe Experience Manager] points de terminaison codés. The names is an encoded version of the targeted [!DNL Adobe Experience Manager] URL. For example, if the application is targeting `localhost:4502` then the directory name will be `localhost_4502`.

To clear the cache, delete the desired Encoded [!DNL Adobe Experience Manager] Endpoint directory. Sinon, la suppression de l’intégralité du répertoire spécifié dans les préférences effacera le cache de toutes les instances utilisées par l’application.

Clearing [!DNL Adobe Experience Manager] desktop app&#39;s cache is a preliminary troubleshooting task that can resolve several issues. Effacez le cache des préférences de l’application. Voir [Définition des préférences](install-upgrade.md#set-preferences). L’emplacement par défaut du dossier de cache est :

### Know the [!DNL Adobe Experience Manager] desktop app version {#know-app-version-v2}

Pour afficher le numéro de version :

1. Démarrez l’application.

1. Cliquez sur les ellipses dans l’angle supérieur droit, passez la souris sur [!UICONTROL Help]l’objet, puis cliquez sur [!UICONTROL About].

   Le numéro de version est répertorié dans cet écran.

### Impossible de voir les ressources importées {#placed-assets-missing}

Si vous ne pouvez pas voir les ressources que vous ou d’autres professionnels de la création avez placées dans les fichiers de support (fichiers INDD, par exemple), vérifiez les éléments suivants :

* Connexion au serveur. Une connectivité réseau défaillante peut bloquer les téléchargements de ressources.

* Taille de fichier. Le téléchargement et l’affichage des ressources volumineuses prennent plus de temps.

* Cohérence des lettres de lecteur. Si vous ou un autre collaborateur avez placé les ressources tout en mappant le DAM AEM sur une autre lettre de lecteur, les ressources placées ne s’affichent pas.

* Permissions. Pour vérifier que vous êtes autorisé à récupérer les ressources placées, contactez votre administrateur AEM.

### Les modifications apportées aux fichiers dans l’interface utilisateur de l’application de bureau ne sont pas répercutées [!DNL Adobe Experience Manager] immédiatement dans {#changes-on-da-not-visible-on-aem}

[!DNL Adobe Experience Manager] l’application de bureau laisse à l’utilisateur le soin de décider quand toutes les modifications apportées à un fichier sont terminées. En fonction de la taille et de la complexité d&#39;un fichier, le transfert de la nouvelle version d&#39;un fichier vers [!DNL Adobe Experience Manager]la version précédente prend beaucoup de temps. La conception de l’application nécessite de réduire au minimum le nombre de transferts d’un fichier entre les deux, plutôt que de deviner quand les modifications du fichier sont terminées et sont téléchargées automatiquement. Il est conseillé à l’utilisateur de réinitialiser le transfert du fichier en [!DNL Adobe Experience Manager] choisissant de télécharger les modifications d’un fichier.

### Problèmes lors de la mise à niveau sous MacOS {#issues-when-upgrading-on-macos}

Des problèmes peuvent parfois survenir lors de la mise à niveau de l’appli de bureau AEM sous macOS. Cela est dû au dossier système hérité de l’appli de bureau AEM, qui empêche le chargement correct des nouvelles versions de l’application. Pour y remédier, les dossiers et fichiers suivants peuvent être supprimés manuellement.

Avant d’exécuter les étapes suivantes, faites glisser l’application `Adobe Experience Manager Desktop` du dossier des applications MacOS vers la corbeille. Ouvrez ensuite le terminal, exécutez la commande suivante et saisissez votre mot de passe lorsque vous y êtes invité.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

### Chargement des fichiers impossible {#upload-fails}

Si vous utilisez une appli de bureau avec AEM 6.5.1 ou version ultérieure, mettez à niveau S3 ou le connecteur Azure vers la version 1.10.4 ou ultérieure. Cela aura pour effet de résoudre le problème d’échec de chargement de fichier lié à [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). Voir [Instructions d’installation](install-upgrade.md#install-v2).

### [!DNL Experience Manager] problèmes de connexion à l’application de bureau {#connection-issues}

Si vous rencontrez des problèmes généraux de connectivité, voici quelques manières d’obtenir plus d’informations sur ce que [!DNL Experience Manager] fait l’application de bureau.

**Vérification du journal des requêtes**

[!DNL Experience Manager] l’application de bureau consigne toutes les requêtes qu’elle envoie, ainsi que le code de réponse de chaque requête, dans un fichier journal dédié.

1. Ouvrez `request.log` le répertoire des journaux de l’application pour afficher ces requêtes.

1. Chaque ligne du journal représente une requête ou une réponse. Les requêtes auront un `>` caractère suivi de l’URL demandée. Les réponses auront un `<` caractère suivi du code de réponse et de l’URL qui ont été demandées. Les demandes et les réponses peuvent faire l’objet d’une correspondance à l’aide du GUID de chaque ligne.

**Vérifier les requêtes chargées par le navigateur intégré de l’application**

La majorité des requêtes de l’application se trouve dans le journal des requêtes. Toutefois, s’il n’y a aucune information utile à ce sujet, il peut s’avérer utile de consulter les requêtes envoyées par le navigateur intégré de l’application.
Consultez la section [](#da-connection-issue-with-saml-aem) SAML pour savoir comment vue ces requêtes.

#### L&#39;authentification de connexion SAML ne fonctionne pas {#da-connection-issue-with-saml-aem}

Si [!DNL Experience Manager] l’application de bureau ne se connecte pas à votre [!DNL Adobe Experience Manager] instance SAML (SSO-enabled), lisez cette section pour résoudre les problèmes. Les processus d’authentification unique sont variés, parfois complexes, et la conception de l’application fait de son mieux pour s’adapter à ces types de connexions. Toutefois, certaines configurations nécessitent un dépannage supplémentaire.

Il arrive que le processus SAML ne redirige pas vers le chemin d’accès initialement demandé ou que la redirection finale soit effectuée vers un hôte différent de celui configuré dans l’application [!DNL Adobe Experience Manager] de bureau. Pour vérifier que ce n&#39;est pas le cas :

1. Ouvrez un navigateur web.

1. Entrez l’URL `<AEM host>/content/dam.json` dans la barre d’adresse.

   Remplacez `<AEM host>` par l’ [!DNL Adobe Experience Manager] instance de cible, par exemple `http://localhost:4502/content/dam.json`.

1. Log in to the [!DNL Adobe Experience Manager] instance.

1. Une fois la connexion terminée, examinez l’adresse actuelle du navigateur dans la barre d’adresse. Il doit correspondre exactement à l’URL qui a été initialement saisie.

1. Vérifiez également que tout ce qui précède `/content/dam.json` correspond à la [!DNL Adobe Experience Manager] valeur de cible configurée dans les paramètres de l’application [!DNL Adobe Experience Manager] de bureau.

**Le processus SAML de connexion fonctionne correctement selon les étapes ci-dessus, mais les utilisateurs ne peuvent toujours pas se connecter.**

La fenêtre de l’application [!DNL Adobe Experience Manager] de bureau qui affiche le processus de connexion est simplement un navigateur Web qui affiche l’interface utilisateur Web de l’instance de cible [!DNL Adobe Experience Manager] :

* La version Mac utilise un [WebView](https://developer.apple.com/documentation/webkit/webview).

* La version Windows utilise [CefSharp](https://cefsharp.github.io/)basé sur le chrome.

Assurez-vous que le processus SAML prend en charge ces navigateurs.

Pour résoudre d’autres problèmes, il est possible de vue les URL exactes que le navigateur tente de charger. Pour afficher ces informations :

1. Suivez les instructions pour lancer l’application en mode [](#enable-debug-mode)débogage.

1. Reproduisez la tentative de connexion.

1. Accédez au répertoire [de](#check-log-files-v2) journaux de l’application.

1. Pour Windows :

   1. Ouvrez &quot;aemcompanionlog.txt&quot;.

   1. Recherchez les messages commençant par &quot;L’adresse du navigateur de connexion a été remplacée par&quot;. Ces entrées contiennent également l’URL chargée par l’application.

   Pour Mac :

   1. `com.adobe.aem.desktop-nnnnnnnn-nnnnnn.log`, où la valeur **n** est remplacée par la valeur du nom de fichier le plus récent.

   1. Recherchez les messages commençant par &quot;cadre chargé&quot;. Ces entrées contiennent également l’URL chargée par l’application.


L’examen de la séquence d’URL en cours de chargement peut aider à résoudre les problèmes au niveau du SAML afin de déterminer ce qui ne va pas.

#### Problème de configuration SSL {#ssl-config-v2}

Les bibliothèques utilisées par l’appli de bureau AEM pour les communications HTTP appliquent le protocole SSL de manière stricte. Parfois, une connexion peut réussir en utilisant un navigateur, mais échouer avec l’appli de bureau AEM. Pour configurer SSL convenablement, installez le certificat intermédiaire manquant dans Apache. Voir [Comment installer un certificat d’autorité de certification intermédiaire dans Apache](https://access.redhat.com/solutions/43575).


Les bibliothèques utilisées par AEM Bureau pour la communication HTTP utilisent une stricte application SSL. Il peut donc y avoir des cas où les connexions SSL réussies par le biais d’un navigateur échouent avec une application [!DNL Adobe Experience Manager] de bureau. Cela est bénéfique car cela encourage la configuration correcte de SSL et augmente la sécurité, mais peut être frustrant lorsque l&#39;application ne parvient pas à se connecter.

Dans ce cas, l’approche recommandée consiste à utiliser un outil pour analyser le certificat SSL d’un serveur et identifier les problèmes afin de les corriger. Certains sites Web inspectent le certificat d’un serveur pour fournir son URL.

A titre de mesure temporaire, il est possible de désactiver l’application SSL stricte dans [!DNL Adobe Experience Manager] les applications de bureau. Il ne s’agit pas d’une solution à long terme recommandée, car elle réduit la sécurité en masquant la cause première d’un protocole SSL mal configuré. Pour désactiver l&#39;application stricte :

1. Utilisez l’éditeur de votre choix pour modifier le fichier de configuration JavaScript de l’application, qui se trouve (par défaut) aux emplacements suivants (selon le système d’exploitation) :

   Sous Mac : `/Applications/Adobe Experience Manager Desktop.app/Contents/Resources/javascript/lib-smb/config.json`

   Sous Windows :`C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop\javascript\config.json`

1. Recherchez la section suivante dans le fichier :

   ```shell
   ...
   "assetRepository": {
       "options": {
   ...
   ```

1. Modifiez la section en ajoutant `"strictSSL": false` ce qui suit :

   ```shell
   ...
   "assetRepository": {
       "options": {
           "strictSSL": false,
   ...
   ```

1. Enregistrez le fichier et redémarrez [!DNL Adobe Experience Manager] l’application de bureau.

### L’application ne répond pas {#unresponsive}

L’application risque rarement de ne plus répondre, d’afficher uniquement un écran blanc ou d’afficher une erreur au bas de l’interface sans aucune option. Procédez comme suit dans l’ordre :

* Cliquez avec le bouton droit sur l’interface de l’application et cliquez sur **[!UICONTROL Refresh]**.
* Quittez l’application et redémarrez-la.

Dans les deux méthodes, l’application démarre au dossier DAM racine.

### Besoin d’aide supplémentaire pour les applications [!DNL Experience Manager] pour postes de travail {#additional-help}

Créez un ticket Jira avec les informations suivantes :

* Utilisez `DAM - Companion App` comme [!UICONTROL Component].

* Cette section décrit les étapes détaillées à suivre pour reproduire le problème dans [!UICONTROL Description].

* Journaux de niveau DEBUG capturés lors de la reproduction du problème.

* Version cible d’AEM.

* Version du système d’exploitation.

* [!DNL Adobe Experience Manager] version d’application de bureau. Pour connaître la version de votre application, reportez-vous à la page [Recherche de la version](#know-app-version-v2)de l’application de bureau.

>[!MORELIKETHIS]
>
>* [Problèmes connus](release-notes.md#known-issues-v2)
>* [Éviter les conflits de modification](using.md#adv-workflow-collaborate-avoid-conflicts)

