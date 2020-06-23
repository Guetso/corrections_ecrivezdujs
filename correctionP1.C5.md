# Voir la correction du [P1.C5](https://openclassrooms.com/fr/courses/5543061-ecrivez-du-javascript-pour-le-web/5578181-recuperez-des-donnees-utilisateur-avec-les-evenements#/id/r-5814309) sur [Codepen](https://codepen.io/joellesenne/pen/pogPzBM)

>Essayons maintenant de gérer un formulaire au travers cet [exercice](https://codepen.io/nicolaspatschkowski/pen/MWwQoQZ).

Ecoutez les événements input sur l'élément `id="name"` afin de savoir quand le contenu du champ texte est changé. Affichez le contenu actuel dans l'élément `id="res-name"`

### Dans le fichier JS
```javascript
// On récupère l'input 'name'
const name = document.getElementById('name');

// On récupère l'élément 'res-name'
const nameResult = document.getElementById('res-name');

// On écoute les inputs sur l'input 'name"
name.addEventListener('input', (event) => {
  // A chaque modification de l'input, le texte s'affiche dans l'élément 'res-name'
  nameResult.innerHTML = event.target.value;
});
```

Maintenant nous voulons écouter l'événement du changement de choix du genre (#gender), et afficher le résultat dans l'élément `id="res-gender"`

```javascript
const gender = document.getElementById('gender');

let genderResult = document.getElementById('res-gender');

gender.addEventListener('input', (event) => {
  genderResult.innerHTML = event.target.value;
});
```

Nous souhaitons maintenant afficher les coordonnées de la souris à l'intérieur de l'élément `id="result"` dès que celle-ci passe par-dessus. Ce que nous voulons, c'est avoir les coordonnées relatives au coin en haut à gauche de l'élément `id="result"`

```javascript
const result = document.getElementById('result');
let mouseX = document.getElementById('mouse-x');
let mouseY = document.getElementById('mouse-y');

result.addEventListener("mousemove", (event) => {
  const x = event.offsetX;

  mouseX.innerHTML = x;

  const y = event.offsetY;

  mouseY.innerHTML = y;
});
```

### Dans le fichier HTML

```html
   <form>
    <div>
      <input type="text" id="name" placeholder="Nom" />
    </div>
    <div>
    <select id="gender">
      <option>Choisissez une valeur</option>
      <option value="male">Homme</option>
      <option value="female">Femme</option>
      <option value="other">Autre</option>
    </select>  
  </div>
</form>
    
<div id="result">
  Nom : <span id="res-name"></span><br />
  Genre : <span id="res-gender"></span><br />
  Souris : (<span id="mouse-x"></span>, <span id="mouse-y"></span>)
</div>
```

### Dans le fichier CSS

```css
body {
  padding: 50px;
}

form, #result {
  margin: auto;
  margin-bottom: 20px;
  padding: 20px;
  width: 300px;
  
  border: solid 1px #0000FF;
  border-radius: 4px;
}

input, select {
  margin: 4px;
  padding: 8px;
  border: solid 1px #0000FF;
  border-radius: 4px;
}

div + span {
  margin: 10px;
}
```
