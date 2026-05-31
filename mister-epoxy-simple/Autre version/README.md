# Mister Epoxy — Site simple

Un seul fichier HTML, pas besoin d'installer quoi que ce soit.

## 🚀 Voir le site tout de suite

**Double-clique sur `index.html`** → ça s'ouvre dans ton navigateur.

C'est tout. Pas de serveur à lancer, pas de terminal.

---

## ✏️ Modifier le site

### 1. Ouvre le fichier dans VS Code
- Lance VS Code
- Fichier → Ouvrir → sélectionne `index.html`

### 2. Repère la partie à modifier
Le fichier est organisé en sections clairement nommées :
```
<!-- NAVBAR -->           ← le menu en haut
<!-- HERO -->             ← la grande section d'accueil
<!-- MARQUEE -->          ← le texte qui défile
<!-- EXPERTISE -->        ← "Une matière noble"
<!-- PRESTATIONS -->      ← les 6 services
<!-- PROJETS -->          ← la galerie
<!-- PROCESSUS -->        ← les 5 étapes
<!-- TÉMOIGNAGES -->      ← les avis clients
<!-- FAQ -->              ← les questions/réponses
<!-- CONTACT -->          ← le formulaire
<!-- FOOTER -->           ← le pied de page
```

**Astuce** : utilise `Cmd + F` dans VS Code pour chercher un texte précis.

### 3. Modifie
Trouve la partie, change le texte. Enregistre avec `Cmd + S`.

### 4. Vois le résultat
Dans ton navigateur, appuie sur `Cmd + R` (ou `F5`) pour recharger la page. C'est instantané.

---

## 🎨 Exemples de modifications

### Changer un texte

Cherche par exemple `Le sol,` et tu vois :
```html
<h1 class="hero-title reveal">
  Le sol,<br>
  <span class="italic-serif">pièce maîtresse</span><br>
  de l'espace.
</h1>
```
Change les mots, enregistre, recharge.

### Changer les couleurs du site

Tout en haut du fichier, cherche `:root {` :
```css
:root {
  --ink: #0a0a0a;        /* noir principal */
  --paper: #ffffff;      /* blanc de fond */
  --bone: #f5f3ef;       /* beige chaud */
  --smoke: #8a8a8a;      /* gris texte secondaire */
}
```
Change les valeurs `#xxxxxx` (ce sont des codes couleur). Tout le site se met à jour.

Pour trouver des codes couleur : [htmlcolorcodes.com](https://htmlcolorcodes.com)

### Mettre ton propre logo

1. Crée un dossier `images` à côté du fichier `index.html`
2. Mets ton logo dedans (appelle-le par exemple `logo.png`)
3. Cherche `<!-- NAVBAR -->` dans le fichier
4. Tu verras :
```html
<a href="#top" class="logo" aria-label="Mister Epoxy - Accueil">
  <span class="logo-mark">M</span>
  <span class="logo-text">Mister Epoxy</span>
</a>
```
5. Remplace les 2 `<span>` par une image :
```html
<a href="#top" class="logo" aria-label="Mister Epoxy - Accueil">
  <img src="images/logo.png" alt="Mister Epoxy" style="height: 40px;">
</a>
```
6. Enregistre, recharge, ton logo apparaît.

### Changer une photo de projet

Cherche par exemple `Loft résidentiel`. Tu verras :
```html
<img src="https://images.unsplash.com/photo-1600566753190..." alt="...">
```

**Option A — utiliser une autre image du web** : remplace l'URL par celle de ton image.

**Option B — utiliser ta propre photo** :
1. Mets ta photo dans le dossier `images/` (crée-le à côté de `index.html` si besoin)
2. Remplace l'URL par `images/ma-photo.jpg`

### Changer les coordonnées

Cherche `+33 (0)1 23 45 67 89` ou `contact@misterepoxy.fr` — tu les verras plusieurs fois. Change partout.

Pour l'adresse, cherche `12 rue des Artisans`.

### Changer un chiffre de la section "stats"

Cherche `540` :
```html
<span class="stat-number">540</span><span class="stat-suffix">+</span>
<div class="stat-label">projets livrés</div>
```
Change le chiffre, le suffixe, ou le label.

---

## ⚠️ Conseils importants

1. **Avant chaque grosse modif**, fais une copie de sauvegarde du fichier (clic droit → Dupliquer). Si tu casses quelque chose, tu peux revenir en arrière.

2. **Ne supprime pas les balises** : `<h1>`, `<p>`, `<div>`, etc. Modifie seulement le texte qui se trouve **entre** elles.

3. **Si tu vois du code bizarre apparaître** à l'écran après une modif, c'est que tu as cassé une balise. Appuie sur `Cmd + Z` dans VS Code pour annuler, ou restaure depuis ta copie de sauvegarde.

---

## 📧 Rendre le formulaire fonctionnel

Actuellement le formulaire affiche juste un "merci" mais n'envoie rien. Pour recevoir vraiment les emails :

1. Va sur [formspree.io](https://formspree.io), crée un compte gratuit
2. Crée un nouveau formulaire, tu obtiens une URL du type `https://formspree.io/f/xyzabc123`
3. Dans `index.html`, cherche `<form class="reveal"` et remplace par :
   ```html
   <form class="reveal" action="https://formspree.io/f/xyzabc123" method="POST">
   ```
4. Supprime `onsubmit="handleSubmit(event)" novalidate` (optionnel)

Les emails arriveront dans ta boîte.

---

## 🌍 Mettre le site en ligne

Quand tu es satisfait :

1. **Option gratuite et simple : Netlify**
   - Va sur [netlify.com](https://netlify.com)
   - Crée un compte
   - Glisse-dépose ton dossier entier (avec `index.html` et le dossier `images/` si tu l'as créé) sur la page "Sites"
   - Ton site est en ligne, tu as une URL du type `ton-site.netlify.app`
   - Tu peux ensuite brancher ton nom de domaine (misterepoxy.fr)

2. **Autre option : OVH, Hostinger, O2switch**
   - Uploade `index.html` (et le dossier `images/`) via FTP à la racine de ton hébergement

---

## 📝 Ce qu'il reste à faire avant mise en ligne

- [ ] Remplacer les images Unsplash par tes vraies photos
- [ ] Mettre tes vraies coordonnées (tel, email, SIRET, adresse)
- [ ] Brancher le formulaire à Formspree ou autre
- [ ] Ajouter une page "Mentions légales" (obligatoire en France)
- [ ] Ajouter une page "Politique de confidentialité" (obligatoire - RGPD)
- [ ] Remplacer le favicon (icône de l'onglet navigateur)
- [ ] Mettre tes vrais témoignages clients

---

Bon courage ! Si tu as une question précise, c'est souvent en cherchant un mot exact avec `Cmd + F` dans VS Code que tu trouves la partie à modifier.
