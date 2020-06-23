# Voir la correction du [P3.C2](https://openclassrooms.com/fr/courses/5543061-ecrivez-du-javascript-pour-le-web/5577676-gerez-du-code-asynchrone#/id/r-6847512) sur [Codepen](https://codepen.io/joellesenne/pen/yLeMPEg)

## Dans cet [exercice](https://codepen.io/nicolaspatschkowski/pen/NWqyaKP) j'ai créé 2 fonctions asynchrones (avec le mot clé async) getNumber1() et getNumber2()

### Dans le fichier JS

```javascript
// Créer une constante qui sera la balise portant l'id="app".
const app = document.getElementById('app');

// Créer la fonction getNumber1() qui returne un "nombre".
const getNumber1 = async (value) => {
  return number = await value;
}

// Créer la fonction getNumber2() qui returne un "nombre".
const getNumber2 = async (value) => {
  return number = await value;
}

// Créer une fonction asynchrone (avec async) qui s'appelle compute et récupérer les résultats des 2 fonctions asynchrones getNumber1() et getNumber2() (avec await) et renvoyer la somme des 2 valeurs récupérées.
const compute = async () => {
  const value1 = await getNumber1(10);
  const value2 = await getNumber2(4);
  return result = `Le résultat vaux ${value1 + value2}`;
  
}

// Appeler notre fonction compute() et utiliser sa valeur de retour comme une Promise pour finalement afficher le résultat de la promesse dans le contenu HTML de l'élément ayant pour ID "result".
compute()
.then(data => app.innerHTML = data)
.catch(error => console.log(`Message : ${error}`))
```
### Dans le fichier HTML
```html
<div id="app"></div>
```

### Et dans le fichier CSS
```css
#app {
  margin: auto;
  margin-top: 40px;
  font-size: 24px;
  text-align: center;
}
```
