# Voir la correction du [P1.C2](https://openclassrooms.com/fr/courses/5543061-ecrivez-du-javascript-pour-le-web/5577476-accedez-aux-elements-du-dom) sur [Codepen](https://codepen.io/joellesenne/pen/yLebVYx)

>Pour afficher une console utiliser le site JSBIN et récopié le HTML et le CSS du codepen de l'[exercice](https://codepen.io/nicolaspatschkowski/pen/OJVOyXZ).

### Dans le fichier JS

Récupérez l'élément ayant pour `id="main-content"` grâce à son ID

```javascript
// On va créer une constante qui sera la balise portant l'ìd="main-content"
const main = document.getElementById('main-content'); 

// Pour s'assurer que l'on récupéré le bon élément, on demande à la console d'afficher une des caractéristique de l'élément <main>, à savoir son contenu de text
console.log(main.textContent); 

// La console affiche "Ce contenu est spécial"
```

Récupérez les éléments ayant pour classe  important

```javascript
// On créer une constante qui regroupera tous les éléments ayant pour class="important"
const important = document.getElementsByClassName('important');

// A la différence du premier cas, ici il y a plusieurs éléments (car plusieurs class="important"), on va isoler le 1er élément de la liste (en JS le premier élément = 0)
const firstImportant = important[0];

// On l'affiche dans la console
console.log(firstImportant.innerText);

// La console affiche un paragraphe de lorem
```

Récupérez les éléments de type  article

```javascript
// On créer une constante qui regroupera tous les éléments ayant pour balise <article>
const article = document.getElementsByTagName('article');

// Il y a plusieurs éléments (car plusieurs class="important"), on va isoler le 1er élément de la liste (en JS le premier élément = 0)
const firstArticle = article[0];

//on l'affiche dans la console
console.log(firstArticle.innerText);

// La console affiche deux paragraphes de lorem
```

Récupérez les éléments de type  li qui sont dans une liste ul ayant la classe  important . Cette liste doit elle-même être dans un article (article)

```javascript
// On fait une recherche des <ul> ayant une class="important" et qui son contenu dans une balise <article>
const liImportant = document.querySelector('article ul.important>li'); 

// On l'affiche dans la console 
console.log(liImportant.innerText);

// La console affiche "Elément 4 ". Rappel : querySelector() ne renvoie que le 1er élément qui correspond à la recherche 
```

En reprenant le résultat de la tâche précédente, récupérez l'élément li suivant de la liste ul

```javascript
// Idem précédent
const liImportant = document.querySelector('article ul.important>li'); 

// On créer une constante qui correspond à l'élément suivant dans la constante précédente.
const liSecond = liImportant.nextElementSibling;

// On l'affiche dans la console 
console.log(liSecond.innerText);

// La console affiche "Elément 5"
```

### Dans le fichier HTML

```html
<article>
  <p class="important">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
</article>
<article>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
  </p>
  <ul>
    <li>Elément 1</li>
    <li>Elément 2</li>
    <li>Elément 3</li>
  </ul>
  <p id="main-content">Ce contenu est spécial.</p>
  <ul class="important">
    <li>Elément 4</li>
    <li>Elément 5</li>
    <li>Elément 6</li>
  </ul>
</article>
<article>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
  <ul>
    <li>Elément 7</li>
    <li>Elément 8</li>
    <li>Elément 9</li>
  </ul>
  </p>
</article>
<p class="important">
  Il n'y a plus d'article
<ul>
  <li>Elément 10</li>
  <li>Elément 11</li>
  <li>Elément 12</li>
</ul>
</p>
```

### Dans le fichier CSS

```css
p, ul {
  margin-top: 10px;
}
li {
  margin-left: 30px;
}
article {
  margin: auto;
  margin-bottom: 20px;
  padding: 10px;
  width: 90%;
  border: 1px solid black;
}

#main-content {
  font-weight: bold;
  color: red;
}

.important {
  font-style: italic;
}

```
