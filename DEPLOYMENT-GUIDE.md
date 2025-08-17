# Guide de Déploiement AssurvVente.shop
## Installation WordPress + WooCommerce + ShopLentor Pro sur Hostinger

Ce guide détaille les étapes pour déployer la plateforme AssurvVente sur Hostinger avec toutes les fonctionnalités développées.

---

## 📋 Prérequis

### Informations nécessaires :
- **Domaine :** assurvente.shop
- **Licence ShopLentor Pro :** 6B984DDA-F9A59116-9174B36E-E1458553
- **API SMS Orange :** 22600f7d6f8f27e9ff44f14609dfabe7
- **Accès Hostinger :** Panneau de contrôle hPanel

### Fichiers à télécharger :
- Tous les fichiers du dossier `wordpress-structure/`
- Plugin ShopLentor Pro (à télécharger avec la licence)

---

## 🚀 Étape 1 : Installation WordPress sur Hostinger

### 1.1. Connexion à hPanel
1. Connectez-vous à votre compte Hostinger
2. Accédez au panneau hPanel
3. Sélectionnez votre domaine assurvente.shop

### 1.2. Installation WordPress
1. Dans hPanel, cliquez sur **"Auto Installer"**
2. Sélectionnez **"WordPress"**
3. Choisissez le domaine **assurvente.shop**
4. Configurez :
   - **Nom du site :** AssurvVente
   - **Description :** Vente d'électroménagers à crédit avec assurance
   - **Nom d'utilisateur admin :** (choisir un nom sécurisé)
   - **Mot de passe admin :** (générer un mot de passe fort)
   - **Email admin :** votre email
5. Cliquez sur **"Installer"**

### 1.3. Configuration SSL
1. Dans hPanel, allez dans **"SSL/TLS"**
2. Activez le **SSL gratuit** pour assurvente.shop
3. Forcez HTTPS dans les paramètres

---

## 🔧 Étape 2 : Configuration WordPress de base

### 2.1. Connexion à l'administration
1. Accédez à `https://assurvente.shop/wp-admin`
2. Connectez-vous avec vos identifiants admin

### 2.2. Configuration générale
1. **Réglages > Général :**
   - Titre du site : **AssurvVente**
   - Slogan : **Électroménagers à crédit avec assurance**
   - URL WordPress : `https://assurvente.shop`
   - URL du site : `https://assurvente.shop`
   - Fuseau horaire : **Dakar**

2. **Réglages > Permaliens :**
   - Sélectionner **"Nom de l'article"**
   - Enregistrer

---

## 📦 Étape 3 : Installation des plugins essentiels

### 3.1. Plugins via le répertoire WordPress
1. **Extensions > Ajouter** et installer :
   - **WooCommerce** (activer et configurer)
   - **Elementor** (version gratuite d'abord)
   - **User Role Editor**
   - **WP Mail SMTP**

### 3.2. Installation ShopLentor Pro
1. Télécharger ShopLentor Pro avec la licence fournie
2. **Extensions > Ajouter > Téléverser une extension**
3. Sélectionner le fichier .zip de ShopLentor Pro
4. Activer et entrer la licence : `6B984DDA-F9A59116-9174B36E-E1458553`

### 3.3. Configuration WooCommerce
1. Suivre l'assistant de configuration WooCommerce
2. **Pays/Région :** Sénégal
3. **Devise :** Franc CFA (XOF) ou FCFA
4. **Méthodes de paiement :** Configurer selon vos besoins
5. **Expédition :** Configurer les zones de livraison

---

## 🎨 Étape 4 : Installation du thème AssurvVente

### 4.1. Téléchargement des fichiers du thème
1. Accéder au **Gestionnaire de fichiers** dans hPanel
2. Naviguer vers `/public_html/wp-content/themes/`
3. Créer un dossier `assurvente-theme`
4. Télécharger les fichiers :
   - `style.css`
   - `functions.php`
   - `index.php` (créer un fichier basique si nécessaire)

### 4.2. Activation du thème
1. **Apparence > Thèmes**
2. Activer **"AssurvVente Child Theme"**

### 4.3. Configuration du thème
1. **Apparence > Personnaliser**
2. Configurer :
   - Logo du site
   - Couleurs (déjà définies dans le CSS)
   - Menus de navigation
   - Widgets

---

## 🔌 Étape 5 : Installation du plugin de crédit

### 5.1. Téléchargement du plugin
1. Dans le **Gestionnaire de fichiers**, naviguer vers `/public_html/wp-content/plugins/`
2. Créer le dossier `assurvente-credit`
3. Télécharger tous les fichiers du plugin :
   ```
   assurvente-credit/
   ├── assurvente-credit.php
   ├── templates/
   │   └── credit-calculator.php
   ├── assets/
   │   ├── css/
   │   │   └── credit-style.css
   │   └── js/
   │       └── credit-calculator.js
   └── admin/
       └── dashboard.php
   ```

### 5.2. Activation du plugin
1. **Extensions > Extensions installées**
2. Activer **"AssurvVente Credit System"**
3. Le plugin créera automatiquement les tables de base de données

---

## 📱 Étape 6 : Configuration SMS Orange

### 6.1. Configuration dans WordPress
1. Aller dans **AssurvVente > Paramètres** (menu admin)
2. Configurer les paramètres SMS :
   - **Token :** 22600f7d6f8f27e9ff44f14609dfabe7
   - **Signature :** (à obtenir d'Orange)
   - **Clé publique :** (à obtenir d'Orange)

### 6.2. Test d'envoi SMS
1. Utiliser l'interface de contrôle à distance dans le dashboard
2. Envoyer un SMS de test
3. Vérifier la réception et les logs

---

## 🛍️ Étape 7 : Configuration des produits

### 7.1. Création des catégories
1. **Produits > Catégories**
2. Créer les catégories d'électroménagers :
   - Réfrigérateurs
   - Lave-linge
   - Cuisinières
   - Climatiseurs
   - Téléviseurs
   - etc.

### 7.2. Ajout des produits
1. **Produits > Ajouter un produit**
2. Pour chaque produit, remplir :
   - **Titre et description**
   - **Prix** (sera utilisé pour le calcul de crédit)
   - **Images produit**
   - **Champs personnalisés :**
     - Numéro de contrôle à distance
     - Statut d'activation
     - Informations d'assurance

### 7.3. Configuration du calculateur
1. Ajouter le shortcode `[assurvente_credit_calculator]` dans la description des produits
2. Ou l'ajouter automatiquement via les hooks WooCommerce (déjà configuré)

---

## 👥 Étape 8 : Gestion des utilisateurs et rôles

### 8.1. Configuration des rôles
1. **Utilisateurs > User Role Editor**
2. Vérifier que les rôles personnalisés sont créés :
   - Partenaire
   - Agent Assurance

### 8.2. Création des utilisateurs de test
1. Créer des comptes pour tester :
   - Un compte Partenaire
   - Un compte Agent Assurance
   - Un compte Client normal

---

## 📄 Étape 9 : Création des pages essentielles

### 9.1. Pages légales (déjà créées automatiquement)
- Termes et Conditions
- Politique de Confidentialité
- Informations Crédit
- Informations Assurance

### 9.2. Pages principales à créer
1. **Page d'accueil :**
   - Utiliser Elementor + ShopLentor
   - Bannière avec calculateur de crédit
   - Grille de produits
   - Témoignages clients

2. **Page Catalogue :**
   - Grille de produits avec filtres ShopLentor
   - Calculateur de crédit intégré

3. **Page À Propos :**
   - Histoire d'AssurvVente
   - Avantages du système de crédit
   - Informations sur l'assurance

---

## ⚡ Étape 10 : Optimisations Hostinger

### 10.1. Cache et Performance
1. **hPanel > Optimisation :**
   - Activer **LiteSpeed Cache**
   - Activer **CDN Hostinger**
   - Compression GZIP (généralement activée par défaut)

### 10.2. Sécurité
1. **hPanel > Sécurité :**
   - Configurer le **Firewall**
   - Activer la **Protection DDoS**
   - Configurer les **sauvegardes automatiques**

### 10.3. Monitoring
1. Configurer les **alertes de monitoring**
2. Vérifier les **logs d'erreur** régulièrement

---

## 🧪 Étape 11 : Tests complets

### 11.1. Tests fonctionnels
- [ ] **Calculateur de crédit :** Tester avec différents montants
- [ ] **Demande de crédit :** Processus complet de soumission
- [ ] **SMS :** Envoi et réception des notifications
- [ ] **Commandes :** Processus d'achat complet
- [ ] **Paiements :** Simulation des échéances
- [ ] **Contrôle à distance :** Interface admin

### 11.2. Tests de performance
- [ ] **Vitesse de chargement :** < 3 secondes
- [ ] **Responsive :** Tous les appareils
- [ ] **SEO :** Optimisation de base

### 11.3. Tests de sécurité
- [ ] **SSL :** Certificat valide
- [ ] **Formulaires :** Protection CSRF
- [ ] **Accès :** Restrictions par rôle

---

## 🔧 Étape 12 : Configuration finale

### 12.1. Variables d'environnement
Ajouter dans `wp-config.php` :
```php
// Configuration AssurvVente
define('ASSURVENTE_SMS_TOKEN', '22600f7d6f8f27e9ff44f14609dfabe7');
define('ASSURVENTE_SMS_SIGNATURE', 'YOUR_SIGNATURE');
define('ASSURVENTE_SMS_PUBLIC_KEY', 'CLE_PUBLIQUE');

// Sécurité renforcée
define('DISALLOW_FILE_EDIT', true);
define('WP_DEBUG', false);
```

### 12.2. Sauvegarde initiale
1. Créer une **sauvegarde complète** du site
2. Exporter la **base de données**
3. Sauvegarder les **fichiers du site**

---

## 📞 Support et Maintenance

### Contacts techniques :
- **Hostinger Support :** Via hPanel
- **Documentation :** Ce guide et les fichiers de code

### Maintenance régulière :
- **Mises à jour :** WordPress, plugins, thèmes
- **Sauvegardes :** Vérification hebdomadaire
- **Monitoring :** Surveillance des performances
- **Sécurité :** Scan régulier des vulnérabilités

---

## 🎯 Checklist de déploiement

- [ ] WordPress installé et configuré
- [ ] SSL activé et forcé
- [ ] WooCommerce configuré (devise FCFA)
- [ ] ShopLentor Pro activé avec licence
- [ ] Thème AssurvVente installé et activé
- [ ] Plugin de crédit installé et fonctionnel
- [ ] SMS Orange configuré et testé
- [ ] Produits ajoutés avec calculateur
- [ ] Rôles utilisateurs configurés
- [ ] Pages essentielles créées
- [ ] Optimisations Hostinger activées
- [ ] Tests complets réalisés
- [ ] Sauvegarde initiale effectuée

---

## 🚨 Dépannage courant

### Problème : Calculateur de crédit ne fonctionne pas
**Solution :** Vérifier que jQuery est chargé et que les scripts sont bien enregistrés

### Problème : SMS ne s'envoient pas
**Solution :** Vérifier les paramètres API Orange et les logs d'erreur

### Problème : Erreur 500
**Solution :** Vérifier les logs d'erreur PHP dans hPanel

### Problème : Site lent
**Solution :** Activer le cache LiteSpeed et optimiser les images

---

**🎉 Félicitations ! AssurvVente.shop est maintenant déployé et opérationnel !**
