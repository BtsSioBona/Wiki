# Supprime oneDrive sur le coté

# Fichier à mettre en .reg
```
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Classes\CLSID\{018D5C66-4533-4307-9B53-224DE2ED1FE6}]
"System.IsPinnedToNameSpaceTree"=dword:00000000

[-HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Desktop\NameSpace\{018D5C66-4533-4307-9B53-224DE2ED1FE6}]

```


```
Appuyez sur la combinaison de touches Windows+R pour ouvrir la fenêtre Exécuter.

Tapez gpedit.msc, puis cliquez sur OK.

Dans l’éditeur de stratégies de groupe local, dans la liste des dossiers sous Stratégie Ordinateur local, parcourez les dossiers pour accéder à Stratégie Ordinateur local > Configuration ordinateur > Modèles d’administration > Composants Windows > OneDrive.

Éditeur de stratégie de groupe local

Dans l’écran OneDrive, sous Paramètre, cliquez sur Empêcher l’utilisation de OneDrive pour le stockage de fichiers.

Dans la boîte de dialogue Empêcher l’utilisation de OneDrive pour le stockage de fichiers, sélectionnez Activé, puis cliquez sur OK.

Paramètre Empêcher l’utilisation de OneDrive

Masquer OneDrive dans Windows 10

OneDrive est intégré à Windows 10. Vous ne pouvez donc pas le désinstaller. En revanche, vous pouvez le masquer et arrêter le processus de synchronisation. Il reste en quelque sorte caché. Pour ce faire, désactivez tous les paramètres OneDrive et supprimez le dossier OneDrive de l’Explorateur de fichiers.

Dans la zone de notification en bas de l’écran de Windows, cliquez avec le bouton droit sur l’icône OneDrive. Vous devrez peut-être cliquer sur la flèche Afficher les icônes cachées pour trouver OneDrive.

Application OneDrive dans la barre d’état système

Cliquez sur Paramètres. Sous l’onglet Paramètres, décochez toutes les cases sous Général.

Sous l’onglet Enregistrement automatique, définissez les listes Documents et images sur Ce PC uniquement, puis décochez les autres cases.

Sous l’onglet Compte, cliquez sur Choisir des dossiers.

Dans la zone Synchroniser vos fichiers OneDrive sur ce PC, cochez et décochez la case Synchroniser tous les fichiers et dossiers dans mon OneDrive. (La première action permet de cocher toutes les cases, puis la deuxième permet de toutes les décocher.) Cliquez sur OK pour fermer la boîte de dialogue et revenir aux paramètres.

Cette étape supprime tous les fichiers OneDrive de votre ordinateur, mais ces derniers restent sur OneDrive.com.

Cliquez sur OK pour enregistrer vos modifications dans la boîte de dialogue Paramètres.

Rouvrez la boîte de dialogue Paramètre : Dans la zone de notification, cliquez avec le bouton droit sur l’icône OneDrive, puis cliquez sur Paramètres. Sous l’onglet Compte, cliquez sur Supprimer le lien vers OneDrive. Fermez la boîte de dialogue Bienvenue dans OneDrive qui s’affiche.

Dans l’Explorateur de fichiers, cliquez avec le bouton droit sur OneDrive, puis cliquez sur Propriétés.

Sous l’onglet Général, en regard de Attributs, cochez la case Caché. Cette action permet de masquer OneDrive dans l’Explorateur de fichiers.

De nouveau, dans la zone de notification, cliquez avec le bouton droit sur l’icône OneDrive, puis cliquez sur Quitter. Cette action supprime l’icône OneDrive de la zone de notification.
```
