# Voir la correction du [P1.C3](https://openclassrooms.com/fr/courses/5543061-ecrivez-du-javascript-pour-le-web/5577491-modifiez-le-dom) sur [Codepen](https://codepen.io/joellesenne/pen/PoZmoyr)

>Entrainez-vous dans l'éditeur de code JavaScript de cet [exercice](https://codepen.io/nicolaspatschkowski/pen/bGdYVmJ).

Créez un nouvel élément de type paragraphe  "p" 

### Dans le fichier JS

```javascript
// On créer la constante qui va générer un élément <p> (sera l'élément enfant)
const newP = document.createElement('p');
```

Ajoutez votre nouvel élément dans l'élément ayant pour `id="app"`

```javascript
// On créer la constante afin de récupérer l'élément existant ayant pour `id="app"` (sera l'élément parent)
const app = document.getElementById('app');

// On affecte <p> en tant qu'enfant de l'élément `<div id="main">`
app.appendChild(newP);

// On vérifie le contenu de la balise <div>, la console affiche `"<p></p>"`
console.log(main.innerHTML);
```


Ajoutez ce contenu HTML dans l'élément que vous avez créé lors de la première tâche :  `Mon <strong>grand</strong> contenu`

```javascript
// Le texte apparait sur la page en gras et rouge
newP.innerHTML = ('Mon <strong>grand</strong> contenu');
```

Ajoutez la classe important à l'élément que vous avez créé lors de la première tâche

```javascript
// Le texte est maintenant en italique
newP.classList.add('important');
```

Modifier la couleur

```javascript
// Le texte est maintenant en vert
newP.style.color = 'green';
```

### Dans le fichier HTML

```html
<div id="main">
```

### Dans le fichier CSS

```css
article {
  margin: auto;
  margin-bottom: 20px;
  padding: 10px;
  width: 90%;
  border: solid 1px #0000FF;
  border-radius: 4px;
}

#app {
  font-weight: bold;
  color: red;
}

.important {
  font-style: italic;
}

```
