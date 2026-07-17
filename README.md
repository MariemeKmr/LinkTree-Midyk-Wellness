# MIDYK Links

Page de liens (type Linktree) pour centraliser tous les canaux MIDYK Wellness :
boutique, Instagram, TikTok, Snapchat, WhatsApp.
Un seul fichier HTML autonome, aucune dependance a installer, aucun build necessaire.

## Fichier

```
index.html
```

Tout est dans ce fichier unique : HTML, CSS et la police (encodee en
base64, integree directement dans le CSS). Aucun autre fichier a copier.

## Identite visuelle

Reprend la charte graphique du site MIDYK Wellness :

| Element | Valeur |
|---------|--------|
| Bordeaux | `#731E1D` |
| Bordeaux fonce | `#5a1616` |
| Vert | `#4D5725` |
| Marron | `#7C6347` |
| Beige | `#EBDED4` |
| Creme | `#FAF6F1` |
| Encre | `#1A1413` |
| Logo "MIDYK" | Police Tan Meringue, couleur bordeaux |
| Corps de texte | DM Sans (Google Fonts) |

## Modifier les liens

Chaque lien est un bloc `<a href="...">` dans le fichier. Cherche la section
`<div class="links">` et modifie les `href` :

```html
<a href="https://instagram.com/midyk.store" ...>
```

| Lien | Ligne a chercher |
|------|-------------------|
| Instagram | `href="https://instagram.com/midyk.store"` |
| TikTok | `href="https://tiktok.com/@midyk.store"` |
| Snapchat | `href="https://snapchat.com/add/midyk.store"` |
| WhatsApp | `href="https://wa.me/221761718393"` |

## Activer le lien boutique

Le lien boutique est actuellement desactive (bloc `<div class="link link-soon">`,
badge "Bientot disponible"). Quand l URL de la boutique est prete :

1. Cherche ce bloc :
```html
<div class="link link-soon" aria-disabled="true">
  ...
  <span>Boutique en ligne</span>
  <span class="soon-tag">Bientot disponible</span>
  ...
</div>
```

2. On le remplacera par un vrai lien, sur le modele des autres :
```html
<a href="https://midyk.store" target="_blank" rel="noopener noreferrer" class="link link-whatsapp">
  <span class="link-icon">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M6 2 3 6v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V6l-3-4Z"/><path d="M3 6h18"/><path d="M16 10a4 4 0 0 1-8 0"/></svg>
  </span>
  <span class="link-label">Visiter la boutique</span>
  <span class="link-arrow">→</span>
</a>
```

`class="link-whatsapp"` donne un fond vert. Utilise `class="link-outline"` pour
un style plus discret, ou cree une nouvelle classe bordeaux si tu veux le mettre
en avant (voir section suivante).

## Modifier la taille du mot "MIDYK"

Cherche `.brand {` dans le `<style>` :

```css
.brand {
  font-family: var(--font-logo);
  font-size: 2rem;
  color: var(--burgundy);
}
```