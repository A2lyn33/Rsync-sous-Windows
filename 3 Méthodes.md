# 🛠️ Tutoriel : Installer et configurer `rsync` sur Windows

`rsync` est un utilitaire puissant pour synchroniser des fichiers et des répertoires entre différents systèmes. Bien qu'il soit principalement conçu pour Linux/Unix, vous pouvez l'utiliser sur Windows grâce à des solutions comme Cygwin ou WSL (Windows Subsystem for Linux).

## ⚙️ Pré-requis
- Un système Windows 10 ou supérieur (idéalement).
- Une connexion Internet active.

## 🚀 Méthodes d'installation

### 1️⃣ Méthode 1 : Installation via WSL (Windows Subsystem for Linux)

1. **Activer WSL sur Windows**
   - Ouvrez PowerShell en mode administrateur.
   - Exécutez la commande suivante :
     ```powershell
     wsl --install
     ```
   - Cela installe la dernière version de WSL ainsi qu'Ubuntu par défaut. Redémarrez si nécessaire.

2. **Configurer Ubuntu (ou une autre distribution)**
   - Lancez l'application "Ubuntu" depuis le menu Démarrer.
   - Suivez les instructions pour créer un utilisateur et définir un mot de passe.

3. **Installer `rsync` sur WSL**
   - Une fois dans le terminal Ubuntu, exécutez :
     ```bash
     sudo apt update && sudo apt install rsync -y
     ```
   - Vérifiez l'installation :
     ```bash
     rsync --version
     ```

4. **Utiliser `rsync` avec WSL**
   - Vous pouvez accéder aux fichiers Windows depuis `/mnt/c` dans WSL. Par exemple :
     ```bash
     rsync -av /mnt/c/Users/VotreNom/Documents/ /mnt/c/Users/VotreNom/Sauvegarde/
     ```

### 2️⃣ Méthode 2 : Installation via Cygwin

1. **Télécharger et installer Cygwin**
   - Rendez-vous sur le site officiel de Cygwin : [https://www.cygwin.com/](https://www.cygwin.com/).
   - Téléchargez le setup correspondant à votre système (32 ou 64 bits).

2. **Configurer Cygwin pour inclure `rsync`**
   - Lancez le programme d'installation.
   - Pendant l'installation :
     - Choisissez un miroir de téléchargement proche de votre région.
     - Dans l'étape de sélection des packages, cherchez `rsync` (utilisez la barre de recherche).
     - Cochez `rsync` pour installation.
   - Complétez l'installation.

3. **Vérifier l'installation**
   - Lancez le terminal Cygwin.
   - Tapez :
     ```bash
     rsync --version
     ```
   - Si la version s'affiche, `rsync` est correctement installé.

4. **Utiliser `rsync` avec Cygwin**
   - Les commandes `rsync` fonctionnent comme sur un système Linux. Par exemple :
     ```bash
     rsync -av /cygdrive/c/Users/VotreNom/Documents/ /cygdrive/c/Users/VotreNom/Sauvegarde/
     ```

### 3️⃣ Méthode 3 : Installation via DeltaCopy

1. **Télécharger DeltaCopy**
   - Rendez-vous sur [https://www.aboutmyip.com/AboutMyXApp/DeltaCopy.jsp](https://www.aboutmyip.com/AboutMyXApp/DeltaCopy.jsp).
   - Téléchargez et installez DeltaCopy, une interface Windows pour `rsync`.

2. **Configurer DeltaCopy**
   - Lancez l'application et configurez vos tâches de synchronisation via l'interface graphique.

3. **Utiliser DeltaCopy**
   - Créez un nouveau profil, spécifiez la source et la destination, et exécutez les tâches directement depuis l'interface.

## 📋 Commandes de base pour `rsync`

Voici quelques commandes courantes que vous pouvez utiliser avec `rsync` :

1. **Synchroniser un dossier source avec un dossier de destination :**
   ```bash
   rsync -av /chemin/vers/source/ /chemin/vers/destination/
   ```

2. **Inclure uniquement les fichiers modifiés :**
   ```bash
   rsync -au /chemin/vers/source/ /chemin/vers/destination/
   ```

3. **Supprimer les fichiers obsolètes dans la destination :**
   ```bash
   rsync -av --delete /chemin/vers/source/ /chemin/vers/destination/
   ```

4. **Utiliser `rsync` via SSH :**
   ```bash
   rsync -av -e ssh /chemin/vers/source/ utilisateur@serveur:/chemin/vers/destination/
   ```

## ✅ Conclusion

Vous avez maintenant plusieurs options pour installer et utiliser `rsync` sur Windows. La méthode via WSL est généralement la plus recommandée car elle offre un environnement proche de Linux. Pour des besoins plus simples ou une interface graphique, DeltaCopy est une excellente alternative.


