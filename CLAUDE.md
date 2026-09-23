# CLAUDE.md

## But du projet

Projet d'apprentissage du « vibecoding » : une page HTML unique, progressive, construite
jour après jour. Elle sert de support pédagogique pour découvrir HTML, CSS (Tailwind) et
JavaScript, en gardant une page vivante et démontrable à chaque étape.

## Stack technique

- **HTML5** statique, un seul fichier : `index.html`
- **Tailwind CSS v4** via CDN navigateur (`@tailwindcss/browser@4`) — aucun build
- **JavaScript vanilla** inline, sans framework ni module
- Aucun `package.json`, aucun gestionnaire de paquets, aucune dépendance à installer
- Git pour l'historique ; `lang="fr"` sur la racine

## Structure des fichiers

```
index.html      # la page entière : <head>, <style>, <body>, <script>
NOTES.md        # notes d'apprentissage de l'auteur (relecture de index.html)
CLAUDE.md       # ce fichier
```

## Conventions de style

- **Thème** : fond `bg-slate-950`, texte `text-slate-100`, `antialiased`
- **Layout** : `flex items-center justify-center`, contenu dans un `max-w-xl`
- **Carte** : `rounded-3xl border border-white/10 bg-white/5 backdrop-blur-xl`
  (glassmorphism), `shadow-2xl shadow-black/40`
- **Décor** : halos `absolute rounded-full blur-3xl` en `bg-indigo-500/25` et
  `bg-fuchsia-500/20`, toujours `pointer-events-none`
- **Palette** : indigo = action principale, sky = compteur, fuchsia = accent décoratif,
  emerald = confirmation et action secondaire (« douce »), slate = neutres
- **Boutons** : `rounded-xl` ; action principale = fond plein `bg-indigo-500` + texte blanc ;
  action secondaire = ghost (`border-<couleur>/40` + `bg-<couleur>/10` + texte teinté)
- **Interactions** : `transition`, `hover:-translate-y-0.5`, `active:translate-y-0`,
  `focus:outline-none focus-visible:ring-2` — toujours conserver les classes de focus
- **Responsive** : mobile d'abord, renforts via `sm:` (`sm:p-12`, `sm:text-5xl`)
- **Animations** : déclarées dans `<style>` en `@keyframes`, exposées en classes
  `.animate-float-in` (0.7s) et `.animate-pop` (0.35s) ; toute animation doit rester
  neutralisée par le bloc `@media (prefers-reduced-motion: reduce)` existant

## Conventions de code

- **Nommage des ID** : kebab-case et explicite — `greet-btn`, `btn-increment`, `btn-reset`,
  `counter-display`, `greeting`
- **JS** : un bloc `<script>` unique en fin de `<body>`, `const` par défaut, `let` seulement
  pour l'état mutable (`let count = 0`)
- **Style** : fonctions nommées pour le rendu (`renderCounter()`), `addEventListener` avec
  fonctions fléchées, récupération des éléments par `getElementById`
- **Commentaires** : en français, uniquement là où l'intention n'est pas évidente
  (ex. le `requestAnimationFrame` et le `void element.offsetWidth`)
- **Accessibilité** : tout contenu mis à jour dynamiquement porte `role="status"` et
  `aria-live="polite"`

## Roadmap

- **Mode sombre** (Jour 5) — ajouter une bascule clair/sombre
- **Migration vers Next.js** (Semaine 3) — sortir du fichier unique

Ces étapes ne sont pas encore commencées : toutes les contraintes ci-dessous
restent en vigueur jusqu'à ce qu'elles soient explicitement lancées.

## Ce que Claude doit faire

- Rester en **fichier unique** et sans build : toute nouvelle fonctionnalité va dans `index.html`
- Utiliser les **classes Tailwind** en priorité ; n'écrire du CSS custom que pour ce que
  Tailwind ne couvre pas (comme les `@keyframes`)
- Écrire l'interface et les commentaires **en français**, dans le ton et la densité du code
  existant
- Réutiliser les classes et la palette déjà présentes plutôt qu'en introduire de nouvelles
- Conserver les attributs d'accessibilité et le respect de `prefers-reduced-motion`
- Limiter la taille du bloc `<script>` : du JS simple et lisible, c'est un support pédagogique

## Ce que Claude ne doit PAS faire

- Ajouter une dépendance, un `package.json`, une étape de build ou un bundler
- Découper la page en plusieurs fichiers, ni externaliser le CSS ou le JS
- Introduire un framework JS (React, Vue…) ou des modules ES
- Casser la structure `<head>` / `<style>` / `<body>` / `<script>`
- Renommer les ID existants ou supprimer des éléments sans raison
- Ajouter des animations sans les brancher sur le bloc `prefers-reduced-motion`
- Réécrire `NOTES.md` : c'est le carnet personnel de l'auteur, il n'est pas généré
