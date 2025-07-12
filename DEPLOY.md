# Guide de Déploiement sur GitHub Pages

## Configuration effectuée

### 1. Configuration Vite (vite.config.ts)
- `base: '/landingPage/'` - Chemin de base pour GitHub Pages
- Configuration de build optimisée

### 2. Package.json
- Script `deploy` ajouté
- Dépendance `gh-pages` installée

### 3. Workflow GitHub Actions
- Déploiement automatique sur push vers `main` et `logo_theme`
- Fichier: `.github/workflows/deploy.yml`

## Étapes de déploiement

### Option 1: Déploiement depuis logo_theme (Actuel)

1. **Pousser votre branche actuelle**
   ```bash
   git add .
   git commit -m "Configuration GitHub Pages"
   git push origin logo_theme
   ```

2. **Activer GitHub Pages**
   - Allez dans Settings > Pages de votre repository
   - Source: "GitHub Actions"
   - Le déploiement se fera automatiquement depuis logo_theme

### Option 2: Fusionner avec main puis déployer

1. **Fusionner avec main**
   ```bash
   git checkout main
   git merge logo_theme
   git push origin main
   ```

2. **Le déploiement se fera automatiquement**

### Option 3: Déploiement manuel

1. **Build et déploiement**
   ```bash
   npm run deploy
   ```

2. **Activer GitHub Pages**
   - Settings > Pages > Source: "Deploy from a branch"
   - Branch: `gh-pages`

## URLs importantes

- **Repository**: `https://github.com/VOTRE-USERNAME/landingPage`
- **Site déployé**: `https://VOTRE-USERNAME.github.io/landingPage/`

## Gestion des branches

### Workflow actuel
- Le déploiement se déclenche sur `main` ET `logo_theme`
- Vous pouvez déployer directement depuis logo_theme
- Une fois satisfait, vous pouvez fusionner avec main

### Nettoyage après fusion
Une fois fusionné avec main, vous pouvez :
```bash
# Supprimer logo_theme du workflow
# Modifier .github/workflows/deploy.yml pour enlever logo_theme
```

## Troubleshooting

### Problème de base URL
Si le nom de votre repository est différent de `landingPage`, modifiez dans `vite.config.ts`:
```typescript
base: '/VOTRE-NOM-DE-REPO/',
```

### Problème d'images
Vérifiez que toutes les images sont dans le dossier `public/` et référencées avec `/nom-image.jpg`

### Problème de déploiement
1. Vérifiez les permissions GitHub Pages dans Settings
2. Assurez-vous que la branche est correcte
3. Vérifiez les logs dans Actions

## Commandes utiles

```bash
# Développement local
npm run dev

# Build de production
npm run build

# Prévisualisation du build
npm run preview

# Déploiement manuel
npm run deploy

# Vérifier la branche actuelle
git branch

# Changer de branche
git checkout main
git checkout logo_theme
```

## Notes importantes

- Le site sera accessible sur `https://VOTRE-USERNAME.github.io/landingPage/`
- Les changements sur `main` OU `logo_theme` déclenchent un déploiement automatique
- Le build est créé dans le dossier `dist/`
- Les assets sont optimisés automatiquement
- Vous pouvez déployer directement depuis logo_theme sans fusionner 