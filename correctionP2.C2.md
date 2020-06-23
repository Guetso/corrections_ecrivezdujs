# Voir la correction du [P2.C2](https://openclassrooms.com/fr/courses/5543061-ecrivez-du-javascript-pour-le-web/5577591-recuperez-des-donnees-dun-service-web#/id/r-5844498) sur [Codepen](https://codepen.io/joellesenne/pen/WNrpBVW)

>Dans cet [exercice](https://codepen.io/nicolaspatschkowski/pen/QWbQMOe) nous voulons récupérer la météo actuelle à Paris et l'afficher dès que nous cliquons sur le bouton "Quelle est la météo sur Paris ?".

### Dans le fichier JS

```javascript
// On récupère l'élément button "ask-weather"
const btn = document.getElementById('ask-weather');

// On récupère l'élément div "weather-result"
const result = document.getElementById('weather-result');

// On créer un EventListener, qui à chaque clique sur le bouton, affichera la météo sur paris
btn.addEventListener('click', () => {
  // Pour cela il va créer une nouvelle requête à chaque clique sur le bouton. 
  const request = new XMLHttpRequest();

  // On va vérifier l'état de la requête
  request.onreadystatechange = function () {
    // Si la requête se termine (DONE) et que son status affiche que tous s'est bien passé (code 200)
    if (this.readyState == XMLHttpRequest.DONE && this.status == 200) {
      // On créer une variable "response" qui contiendra les résultat de la requête transformer d'un format JSON en objet JavaScript(JSON.parse)
      const response = JSON.parse(this.responseText);

      // On affiche le résultat dans l'élément "result", on ne s'interesse ici qu'à un élément de la réponse : "current_condition.condition" qui contient le mot exprimant l'état de la météo actuelle.
      result.innerHTML = response.current_condition.condition;
    }
  };

  // la requête va récupérer dans l'URL spécifié la météo de paris (GET)
  request.open("GET", "https://www.prevision-meteo.ch/services/json/paris");

   // la requête est envoyé au serveur
  request.send();
});
```

### Dans le fichier HTML

```html
<div>
  <button id="ask-weather">Quelle est la météo sur Paris ?</button>
</div>
<div id="weather-result"></div>
```

### Dans le fichier CSS

```css
#ask-weather {
  display: block;
  margin: 20px auto;
  padding: 8px;
  color: #FFF;
  background-color: #0000FF;
  border-radius: 4px;
  cursor: pointer;
}

#weather-result {
  text-align: center;
  font-size: 24px;
}


```
