# LaToile — Exercice HTML

Le CSS est déjà écrit dans `style.css`. Votre mission : écrire le fichier `index.html` pour que le design s'affiche correctement.

> Ouvrez la maquette Figma pour vous guider visuellement :
> https://www.figma.com/design/T4TgalkGTYrvxpghmwTPUg/Portfolio

---

## Structure globale de la page

```
<html>
  <head>        → métadonnées, polices, lien CSS
  <body>
    <nav>       → barre de navigation
    <header>    → section hero (titre principal)
    <main>      → contenu principal
      <section> → compétences
      <section> → projets
      <section> → parcours
    <footer>    → pied de page
```

---

## 1. `<head>`

Le `<head>` doit contenir :
- L'encodage UTF-8
- La balise viewport pour le responsive
- Le titre de la page : **Portfolio**
- Les balises Google Fonts pour charger **Montserrat** (poids : 400, 500, 600, 700, 800)
- Le lien vers `style.css`

---

## 2. Navigation `<nav class="navbar">`

```
nav.navbar
├── a.logo              → texte "LOGO", lien vers "#"
├── ul.nav-links
│   ├── li > a          → "MES COMPÉTENCES ↗"  href="#competences"
│   ├── li > a          → "MES PROJETS ↗"       href="#projets"
│   └── li > a          → "MON PARCOURS ↗"      href="#parcours"
└── a.btn-nav           → "CONTACTEZ MOI ↗"     href="#contact"
```

---

## 3. Hero `<header id="hero">`

```
header#hero
├── h1
│   ├── texte : "Je donne "
│   ├── em              → "vie"   ← balise italique Georgia
│   ├── <br>
│   └── texte : "à vos idées"
└── p                   → "Je travail avec vous pour construire vos projet numériques"
```

> ⚠️ Le mot *vie* est dans une balise `<em>` — c'est ce qui lui applique la police Georgia en italique.

---

## 4. Compétences `<section id="competences" class="competences">`

La section contient **2 cartes** identiques en structure :

```
section#competences.competences
├── div.competence-card
│   ├── h3              → "UI/UX design"
│   ├── p               → Lorem ipsum...
│   └── div.tags
│       ├── span.tag    → "UI/UX design"
│       ├── span.tag    → "Identité graphique"
│       ├── span.tag    → "prototypage"
│       └── span.tag    → "design interactif"
│
└── div.competence-card
    ├── h3              → "Intégrateur front end"
    ├── p               → Lorem ipsum...
    └── div.tags
        ├── span.tag    → "Javascript"
        ├── span.tag    → "HTML/CSS"
        ├── span.tag    → "Python"
        └── span.tag    → "Ruby"
```

---

## 5. Projets `<section id="projets" class="projets">`

La section contient un titre `<h2>` puis **3 cartes projet** (`<article>`).

### Structure d'une carte projet

```
article.projet-card
├── div.projet-content
│   ├── div.projet-top
│   │   ├── h3          → nom du projet
│   │   └── div.tags
│   │       ├── span.tag → "Web design"
│   │       └── span.tag → "Development"
│   └── div.projet-bottom
│       ├── p           → Lorem ipsum...
│       └── a.btn-projet → "VOIR LE PROJET ↗"   href="#"
└── div.projet-image
    └── img             → src="assets/project-img.jpeg"
```

### Ordre des cartes

| Carte | Classe | Image | Contenu | Nom |
|-------|--------|-------|---------|-----|
| Projet 1 | `projet-card` | droite | gauche | Album musique |
| Projet 2 | `projet-card reverse` | **gauche** | droite | Sneakershop |
| Projet 3 | `projet-card` | droite | gauche | Site vitrine |

> ⚠️ Pour le **Projet 2** (`.reverse`), l'image doit être **avant** le contenu dans le HTML :
> ```html
> <article class="projet-card reverse">
>   <div class="projet-image">...</div>   ← image EN PREMIER
>   <div class="projet-content">...</div>
> </article>
> ```

---

## 6. Parcours `<section id="parcours" class="parcours">`

```
section#parcours.parcours
├── h2                  → "Mon parcours"
└── ul.parcours-liste
    ├── li.parcours-item
    │   ├── p.parcours-titre → "2022 - intitulé diplome / poste"
    │   └── p.parcours-lieu  → "ENTREPRISES / ÉCOLE"
    ├── li.parcours-item
    │   └── ...
    ├── li.parcours-item
    │   └── ...
    └── li.parcours-item
        └── ...
```

> 4 items au total, même structure pour chacun.

---

## 7. Footer `<footer class="navbar">`

Même contenu que la `<nav>`, mais dans une balise `<footer>` :

```
footer.navbar
├── span.logo           → "LOGO"   (span, pas un <a> ici)
├── ul.nav-links
│   ├── li > a          → "MES COMPÉTENCES ↗"
│   ├── li > a          → "MES PROJETS ↗"
│   └── li > a          → "MON PARCOURS ↗"
└── a.btn-nav           → "CONTACTEZ MOI ↗"
```

---

## Checklist finale

- [ ] Le fichier s'appelle bien `index.html`
- [ ] La police Montserrat est chargée depuis Google Fonts
- [ ] `style.css` est bien lié dans le `<head>`
- [ ] Le `<em>vie</em>` est présent dans le `<h1>`
- [ ] La carte Projet 2 a la classe `reverse` et l'image est en premier dans le HTML
- [ ] Les `id` de sections correspondent : `#competences`, `#projets`, `#parcours`
- [ ] Le footer utilise `<footer class="navbar">` (pas une balise `<nav>`)
- [ ] Le dossier `assets/` contient une image `project-img.jpeg`
