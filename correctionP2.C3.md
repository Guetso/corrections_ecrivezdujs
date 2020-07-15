# Voir la correction du [P2.C3](https://openclassrooms.com/fr/courses/5543061-ecrivez-du-javascript-pour-le-web/5577611-validez-les-donnees-saisies-par-vos-utilisateurs#/id/r-5853153) sur [Codepen](https://codepen.io/joellesenne/pen/dyGvdoX)

>Voici un [exercice](https://codepen.io/nicolaspatschkowski/pen/GRJQvGY) pour vous faire les dents sur la validation 😎.

### Dans le fichier JS

```javascript
// On définit la constante code qui est l'input du code à saisir
const code = document.getElementById('code');

// On définit la constante code qui est le texte qui affichera si le code est valide
const codeValide = document.getElementById('code-validation');

// On créer un "écouteur d'événement sur chaque input qui va vérifier si le texte saisie dans l'input "code" commence bien par "CODE-"
code.addEventListener('input', (code) => {
  // On créer une règle RegExp avec la string obligatoire en début d'input
  const codeRgex = RegExp(/^CODE-/);

  // On créer une variable qui va vérifier si le paramètre (code) de notre fonction répond à la règle fixée par la RegExp
  let codeResult = codeRgex.test(code.target.value);

  // On a besoin de faire appel à notre bouton de soumission pour la règle suivante
  const submit = document.getElementById('submit-btn');

  // On ajoute par défaut, l'attribut "disabled" à notre boutton de soumssion, par défaut, il est grisé
  submit.setAttribute('disabled', 'true');

  // Si le résultat de notre constante "code" commence par "CODE-"
  if (codeResult === true) {
    // Alors un texte "Code valide" s'affiche dans la zone "code-validation"
    codeValide.innerHTML = 'Code valide';

    // Et l'on supprime l'attribut "disabled", le bouton n'est plus grisé.
    submit.removeAttribute('disabled');
  } else {
    // Sinon le texte affiche "Code invalide", le bouton reste grisé
    codeValide.innerHTML = 'Code invalide';
  }
});
```

### Dans le fichier HTML

```html
<form id="form-to-check">
  <p>
    <label>Code : 
      <input type="text" name="code" id="code" />
    </label>
    <br />
    <div class="result" id="code-validation"></div>
  </p>
  <p>
    <!--On a remplacé la valeur "text" par la valeur "email" dans l'attribut "type"-->
    <label>Email : 
      <input type="email" name="email" required />
    </label>
  </p>
  <p>
    <input type="submit" value="Vérifier" id="submit-btn" />
  </p>
</form>
```

### Dans le fichier CSS

```css

form {
  margin: auto;
  max-width: 300px;
  margin-top: 40px;
}

.result {
  text-align: center;
}

```
