# Voir la correction du [P2.C4](https://openclassrooms.com/fr/courses/5543061-ecrivez-du-javascript-pour-le-web/5577626-sauvegardez-des-donnees-sur-le-service-web#/id/r-5858771) sur [Codepen](https://codepen.io/joellesenne/pen/xxZqpdM)

>Dans cet [exercice](https://codepen.io/nicolaspatschkowski/pen/OJVQjBq) nous voulons pouvoir entrer du texte dans le formulaire et l'envoyer vers un service web. Ce service web va simplement nous renvoyer notre contenu en plus d'autres informations et nous allons afficher le contenu renvoyé par le serveur.

### Dans le fichier JS

```javascript
// Créer une constante qui sera la balise portant l'id="value".
const input = document.getElementById('value');

// Créer une constante qui sera la balise portant l'id="form".
const form = document.getElementById('form');

// Créer une constante qui sera la balise portant l'id="result".
const result = document.getElementById('result');

// Soumettons le formulaire ayant pour id="form".
form.addEventListener('submit', (event) => {

  // Annuler le comportement par défaut de la soumission du formulaire.
  event.preventDefault();

  // Créer une requête avec la fonction  "XMLHttpRequest()".
  const request = new XMLHttpRequest();

  // Créer une requête de type "POST" vers l'adresse suivante : "https://mockbin.com/request",
  request.open('POST', 'https://mockbin.com/request');

  // et y envoyer un contenu JSON ayant une propriété "value".
  request.setRequestHeader('Content-Type', 'application/json');

  // Créer une fonction appelée "send()" et qui va créer notre objet AJAX.
  request.send(JSON.stringify(input.value));

  // Lorsque la requête à bien était envoyée, afficher le résultat renvoyé par le service web.
  request.onreadystatechange = function () {
    if (this.readyState == XMLHttpRequest.DONE && this.status == 200) {
      const response = JSON.parse(this.responseText);
      
      // Afficher ce qui se trouve dans postData.text de la réponse dans le contenu HTML de l'élément ayant pour id="result".
      result.innerHTML = `Le résultat vaux : ${response.postData.text}`;
    }
  };
});
```

### Dans le fichier HTML

```html
<form id="form">
  <label>Saisissez une valeur 
    <input type="text" id="value" />
  </label>
  <br />
  <input type="submit" value="Envoyer" />
</form>
<div id="result"></div>
```

### Et dans le fichier CSS

```css
form {
  max-width: 300px;
  margin: auto;
  margin-top: 30px;
}

input[type="submit"] {
  margin-top: 20px;
  margin-bottom: 20px;
}

#result {
  margin-top 40px;
  text-align: center;
}

```
