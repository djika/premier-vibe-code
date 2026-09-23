# Mes notes — Semaine 2 Jour 2

## Structure de index.html

- Ligne 1 : `<!DOCTYPE html>` → déclare HTML5
- Ligne 2 : `<html lang="fr">` → racine, langue français
- Lignes 3-8 : `<head>` → métadonnées
  - charset UTF-8 (accents)
  - viewport (mobile)
  - title (onglet)
  - script Tailwind CDN (CSS)
- Lignes 9-19 : `<style>` → 2 animations CSS
  - float-in : apparition en douceur
  - pop : effet rebond
- Lignes 20-88 : `<body>` → contenu visible
  - h1 : [texte exact]
  - p : [texte exact]
  - button : [texte + comportement]

## Ce que j'ai compris

- À quoi sert le `<head>` : ...
- À quoi sert le `<body>` : ...
- Comment fonctionne `@keyframes` : ...
- Comment Tailwind est chargé : ...

## Concepts avancés découverts

### Accessibilité (a11y)
- `role="status"` + `aria-live="polite"` sur le paragraphe de greeting
- Permet aux lecteurs d'écran d'annoncer le "Bonjour !"

### Préférences utilisateur
- `@media (prefers-reduced-motion: reduce)` → désactive les animations
- Respecte les utilisateurs sensibles au mouvement

### Tailwind — classes clés
- `bg-white/5` → blanc à 5% d'opacité
- `backdrop-blur-xl` → effet verre flouté (glassmorphism)
- `bg-clip-text text-transparent` → dégradé sur le texte

### JavaScript dynamique
- `requestAnimationFrame` → attend le prochain repaint
- `void element.offsetWidth` → force le recalcul (astuce pro)
- `classList.add('animate-pop')` → ajoute une animation au clic

### Structure
- HTML + CSS + JS dans un seul fichier (single-file)
- Pas de "code mort" : tout est utilisé

## Ce que je n'ai pas compris

## Jour 3 — Compteur interactif

### Concept : l'état (state)
- Un état = une donnée qui change et impacte l'UI
- Cycle : [État initial] → [Événement] → [État modifié] → [UI mise à jour]

### Implémentation du compteur
- Variable JS : `let count = 0;`
- Bouton +1 : `count++; updateDisplay();`
- Bouton Reset : `count = 0; updateDisplay();`
- Fonction `updateDisplay()` : met à jour le texte du `<span>`

### Ce que j'ai appris
- Séparer la logique (état) de l'affichage (DOM)
- Utiliser `addEventListener` sur plusieurs boutons
- Le DOM se met à jour à chaque changement d'état
- ...
