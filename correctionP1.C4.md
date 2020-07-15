# Voir la correction du [P1.C4](https://openclassrooms.com/fr/courses/5543061-ecrivez-du-javascript-pour-le-web/5578156-ecoutez-des-evenements#/id/r-5814294) sur [Codepen](https://codepen.io/joellesenne/pen/PoZmoOL)

>Essayons maintenant de gérer un formulaire au travers cet [exercice](https://codepen.io/nicolaspatschkowski/pen/yLNvXMx).

Commencez par écouter les événements click depuis l'élément `id="parent"`. Puis affichez le nombre de clics dans l'élément `id="parent-count"`

### Dans le fichier JS

```javascript
// On récupère l'élément 'parent' qui correspond au cadre entier
const parent = document.getElementById('parent');

// On récupère l'élément 'parent-count' qui correspond au compteur "Parent"
const parentCount = document.getElementById('parent-count');

// On créer une variable qui correspond à la valeur en 'number' du compteur et on l'initialise à 0
let parentCountValue = 0;

// On créer un EventListener qui écoutera les clics sur le cadre entier ('parent') ; A chaque clic on executera la fonction suivante:
parent.addEventListener('click', () => {
  // La valeur de parentCountValue augmente de 1
  parentCountValue++;

  // On affiche la valeur de parentCountValue dans l'élément 'parent-count'
  parentCount.textContent = parentCountValue;
});
```

Faites la même chose, mais avec l'élément `id="child"`

```javascript
const child = document.getElementById('child');

const childCount = document.getElementById('child-count');

let childCountValue = 0;

child.addEventListener('click', () => {
 childCountValue++;

 childCount.textContent = childCountValue;
});
```

Maintenant, faites de sorte que lorsque vous cliquez sur l'enfant, seul le compteur de l'enfant se mette à jour

```javascript
// On ajoute le paramètre 'event' afin de pouvoir agir dessus
child.addEventListener('click', (event) => {

  // On précise que l'on veut que cet 'event' ne se propage pas à son parent
  event.stopPropagation();

  childCountValue++;

  childCount.textContent = childCountValue;
});
```

Evitez qu'un clic sur le lien ne vous fasse changer de page: supprimez ce comportement par défaut.

```javascript
child.addEventListener('click', (event) => {

  event.stopPropagation();

  event.preventDefault();

  childCountValue++;

  childCount.textContent = childCountValue;
});
```

### Dans le fichier HTML

```html
<article id="parent">
  <a class="link" id="child" href="#">Cliquez ici</a>
  <p>Battle d'événement !</p>
  Parent : <span id="parent-count">0</span>
  Enfant : <span id="child-count">0</span>
</article>
```

### Dans le fichier CSS

```css

body {
  padding: 50px;
}

article {
  margin: auto;
  width: 300px;
  padding: 20px;
  border: solid 1px #0000FF;
  border-radius: 4px;
}

.link {
  float: right;
  margin-left: 30px;
}

p + span {
  margin: 10px;
}
```
