# Guide de Téléchargement et Installation AssurvVente.shop
## Comment récupérer et déployer tous les fichiers sur Hostinger

Ce guide explique comment télécharger et transférer tous les fichiers développés vers votre hébergement Hostinger.

---

## 📥 Méthode 1 : Téléchargement via GitHub (Recommandée)

### Étape 1 : Créer un repository GitHub
1. Créez un compte GitHub si vous n'en avez pas
2. Créez un nouveau repository privé nommé `assurvente-shop`
3. Uploadez tous les fichiers du dossier `wordpress-structure/`

### Étape 2 : Cloner sur Hostinger
1. Connectez-vous à **hPanel Hostinger**
2. Allez dans **"Gestionnaire de fichiers"**
3. Ouvrez le **Terminal** (icône en haut à droite)
4. Naviguez vers votre dossier web :
   ```bash
   cd public_html
   ```
5. Clonez le repository :
   ```bash
   git clone https://github.com/votre-username/assurvente-shop.git temp-assurvente
   ```
6. Copiez les fichiers :
   ```bash
   cp -r temp-assurvente/wordpress-structure/* .
   rm -rf temp-assurvente
   ```

---

## 📥 Méthode 2 : Téléchargement direct via Gestionnaire de fichiers

### Étape 1 : Préparer les fichiers
1. **Créez un dossier** sur votre ordinateur nommé `assurvente-files`
2. **Copiez tous les fichiers** de la structure suivante :

```
assurvente-files/
├── themes/
│   └── assurvente-theme/
│       ├── style.css
│       └── functions.php
├── plugins/
│   └── assurvente-credit/
│       ├── assurvente-credit.php
│       ├── templates/
│       │   └── credit-calculator.php
│       ├── assets/
│       │   ├── css/
│       │   │   └── credit-style.css
│       │   └── js/
│       │       └── credit-calculator.js
│       └── admin/
│           └── dashboard.php
└── contract-terms.php
```

### Étape 2 : Créer les archives ZIP
1. **Thème :** Sélectionnez le dossier `assurvente-theme` → Clic droit → "Compresser" → `assurvente-theme.zip`
2. **Plugin :** Sélectionnez le dossier `assurvente-credit` → Clic droit → "Compresser" → `assurvente-credit.zip`

### Étape 3 : Upload via Gestionnaire de fichiers Hostinger
1. Connectez-vous à **hPanel**
2. Cliquez sur **"Gestionnaire de fichiers"**
3. Naviguez vers `/public_html/wp-content/`

#### Upload du thème :
1. Allez dans `/public_html/wp-content/themes/`
2. Cliquez sur **"Téléverser"**
3. Sélectionnez `assurvente-theme.zip`
4. Une fois uploadé, clic droit sur le fichier → **"Extraire"**
5. Supprimez le fichier ZIP après extraction

#### Upload du plugin :
1. Allez dans `/public_html/wp-content/plugins/`
2. Cliquez sur **"Téléverser"**
3. Sélectionnez `assurvente-credit.zip`
4. Une fois uploadé, clic droit sur le fichier → **"Extraire"**
5. Supprimez le fichier ZIP après extraction

#### Upload du contrat :
1. Allez dans `/public_html/wp-content/themes/`
2. Téléversez `contract-terms.php`

---

## 📥 Méthode 3 : Via FTP (Pour utilisateurs avancés)

### Étape 1 : Obtenir les informations FTP
1. Dans **hPanel**, allez dans **"Comptes FTP"**
2. Notez les informations :
   - **Serveur :** ftp.votre-domaine.com
   - **Nom d'utilisateur :** votre-username
   - **Mot de passe :** votre-password
   - **Port :** 21

### Étape 2 : Utiliser un client FTP
1. Téléchargez **FileZilla** (gratuit)
2. Connectez-vous avec les informations FTP
3. Naviguez vers `/public_html/wp-content/`
4. Transférez les dossiers :
   - `assurvente-theme/` → `/themes/`
   - `assurvente-credit/` → `/plugins/`
   - `contract-terms.php` → `/themes/`

---

## 🔧 Méthode 4 : Copier-coller direct (Fichier par fichier)

### Pour chaque fichier :

#### 1. Thème - style.css
1. **Gestionnaire de fichiers** → `/public_html/wp-content/themes/`
2. **Créer un dossier** → `assurvente-theme`
3. **Entrer dans le dossier** → **Nouveau fichier** → `style.css`
4. **Éditer le fichier** → Copier tout le contenu de `wordpress-structure/assurvente-theme/style.css`
5. **Sauvegarder**

#### 2. Thème - functions.php
1. Dans `/public_html/wp-content/themes/assurvente-theme/`
2. **Nouveau fichier** → `functions.php`
3. **Éditer** → Copier le contenu de `wordpress-structure/assurvente-theme/functions.php`
4. **Sauvegarder**

#### 3. Plugin principal
1. **Gestionnaire de fichiers** → `/public_html/wp-content/plugins/`
2. **Créer un dossier** → `assurvente-credit`
3. **Nouveau fichier** → `assurvente-credit.php`
4. **Éditer** → Copier le contenu de `wordpress-structure/plugins/assurvente-credit/assurvente-credit.php`
5. **Sauvegarder**

#### 4. Répéter pour tous les autres fichiers :
- `templates/credit-calculator.php`
- `assets/css/credit-style.css`
- `assets/js/credit-calculator.js`
- `admin/dashboard.php`
- `contract-terms.php`

---

## ✅ Vérification après upload

### 1. Vérifier la structure des fichiers
Dans le **Gestionnaire de fichiers**, vérifiez que vous avez :
```
/public_html/wp-content/
├── themes/
│   └── assurvente-theme/
│       ├── style.css ✓
│       └── functions.php ✓
├── plugins/
│   └── assurvente-credit/
│       ├── assurvente-credit.php ✓
│       ├── templates/
│       │   └── credit-calculator.php ✓
│       ├── assets/
│       │   ├── css/
│       │   │   └── credit-style.css ✓
│       │   └── js/
│       │       └── credit-calculator.js ✓
│       └── admin/
│           └── dashboard.php ✓
└── contract-terms.php ✓
```

### 2. Vérifier les permissions
1. **Clic droit** sur chaque dossier → **"Permissions"**
2. **Dossiers :** 755 (rwxr-xr-x)
3. **Fichiers :** 644 (rw-r--r--)

### 3. Activer dans WordPress
1. Connectez-vous à `/wp-admin`
2. **Apparence > Thèmes** → Activer **"AssurvVente Child Theme"**
3. **Extensions** → Activer **"AssurvVente Credit System"**

---

## 🚨 Résolution des problèmes courants

### Problème : "Fichier non trouvé"
**Solution :** Vérifiez que tous les fichiers sont dans les bons dossiers avec les bons noms

### Problème : "Erreur de permissions"
**Solution :** 
```bash
# Via Terminal Hostinger
chmod 755 wp-content/themes/assurvente-theme
chmod 644 wp-content/themes/assurvente-theme/*
chmod 755 wp-content/plugins/assurvente-credit
chmod -R 644 wp-content/plugins/assurvente-credit/*
```

### Problème : "Plugin ne s'active pas"
**Solution :** Vérifiez que le fichier principal `assurvente-credit.php` est bien présent et contient l'en-tête du plugin

### Problème : "Thème ne s'affiche pas"
**Solution :** Vérifiez que `style.css` contient bien l'en-tête du thème avec "Theme Name:"

---

## 📋 Checklist de téléchargement

- [ ] **Thème AssurvVente uploadé** dans `/wp-content/themes/assurvente-theme/`
- [ ] **Plugin Crédit uploadé** dans `/wp-content/plugins/assurvente-credit/`
- [ ] **Contrat uploadé** dans `/wp-content/themes/contract-terms.php`
- [ ] **Permissions correctes** (755 pour dossiers, 644 pour fichiers)
- [ ] **Thème activé** dans WordPress admin
- [ ] **Plugin activé** dans WordPress admin
- [ ] **Test du calculateur** sur une page produit
- [ ] **Test du contrat** au checkout
- [ ] **Test SMS** depuis l'admin

---

## 🎯 Fichiers essentiels à ne pas oublier

### Obligatoires pour le fonctionnement :
1. **`assurvente-theme/style.css`** - Design complet
2. **`assurvente-theme/functions.php`** - Fonctionnalités SMS + Contrat
3. **`assurvente-credit/assurvente-credit.php`** - Plugin principal
4. **`contract-terms.php`** - Contrat complet

### Importants pour l'expérience utilisateur :
5. **`credit-calculator.php`** - Interface calculateur
6. **`credit-style.css`** - Styles du calculateur
7. **`credit-calculator.js`** - Interactions JavaScript
8. **`dashboard.php`** - Interface admin

---

## 🔄 Mise à jour des fichiers

Pour mettre à jour un fichier après modification :
1. **Éditez le fichier** localement
2. **Gestionnaire de fichiers Hostinger**
3. **Naviguez vers le fichier**
4. **Clic droit** → **"Éditer"**
5. **Remplacez le contenu**
6. **Sauvegarder**

Ou utilisez FTP pour remplacer le fichier entier.

---

**🎉 Une fois tous les fichiers uploadés, suivez le DEPLOYMENT-GUIDE.md pour la configuration complète !**
