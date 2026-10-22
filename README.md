# Future Coders: Créer son site web

# ⚡ JavaScript : rends ton site interactif !

Tu as déjà créé ton site avec **HTML** et **CSS**. Maintenant, tu peux lui donner vie avec **JavaScript** ! 🚀

JavaScript permet par exemple de :
- Faire réagir un bouton lorsqu'on clique dessus.
- Changer du texte, des couleurs ou des images.
- Afficher ou cacher des éléments.
- Créer des compteurs, des quiz et des mini-jeux.

**Ton objectif :** ajouter au moins une interaction à ton propre site. Tu es libre de choisir laquelle !

## 1. Ajouter JavaScript à ton projet

Tu as normalement déjà ces deux fichiers :

```text
📁 mon-site/
├── index.html
└── style.css
```

Crée un troisième fichier, appelé `script.js` :

```text
📁 mon-site/
├── index.html
├── style.css
└── script.js
```

Dans `index.html`, juste avant `</body>`, ajoute :

```html
<script src="script.js"></script>
```

C'est tout ! Ton HTML est maintenant connecté à JavaScript.

## 2. Ton premier bouton interactif 🖱️

Dans `index.html` :

```html
<button onclick="direBonjour()">Clique ici !</button>
```

Dans `script.js` :

```javascript
function direBonjour() {
    alert("Salut ! 👋");
}
```

Ouvre ton site dans le navigateur et clique sur le bouton !

**Comment ça fonctionne ?**

- `onclick` indique ce qui doit se passer lors d'un clic.
- `direBonjour()` est le nom de notre fonction.
- `function` permet de créer une fonction.
- `alert()` affiche un message.

Une fonction est simplement un ensemble d'instructions qu'on peut exécuter quand on en a besoin.

## 3. Modifier du texte ✏️

Dans `index.html` :

```html
<h1 id="titre">Bienvenue sur mon site !</h1>

<button onclick="changerTitre()">
    Surprise !
</button>
```

Dans `script.js` :

```javascript
function changerTitre() {
    document.getElementById("titre").textContent =
        "Tu as cliqué sur le bouton ! 🎉";
}
```

`document.getElementById("titre")` permet de retrouver l'élément HTML qui possède `id="titre"`.

`textContent` permet de modifier son texte.

### 🎯 À essayer

Modifie le code pour que le bouton affiche un message de ton choix.

## 4. Modifier les couleurs 🎨

JavaScript peut aussi modifier le CSS !

Dans `index.html` :

```html
<h1 id="titre">Mon super site</h1>

<button onclick="changerCouleur()">
    Changer la couleur
</button>
```

Dans `script.js` :

```javascript
function changerCouleur() {
    document.getElementById("titre").style.color = "red";
}
```

Tu peux également modifier la couleur de fond :

```javascript
function changerFond() {
    document.body.style.backgroundColor = "lightblue";
}
```

Ajoute un bouton pour appeler cette fonction !

### 🎯 À essayer

Crée plusieurs boutons qui changent les couleurs de ton site.

## 5. Modifier plusieurs éléments avec une classe 🧩

Un `id` identifie un élément particulier. Une `class` peut être utilisée sur **plusieurs éléments**.

Dans `index.html` :

```html
<p class="carte">Première carte</p>
<p class="carte">Deuxième carte</p>
<p class="carte">Troisième carte</p>
<button onclick="colorierCartes()">Colorier les cartes</button>
```

Dans `script.js` :

```javascript
function colorierCartes() {
    document.querySelectorAll(".carte").forEach(function(carte) {
        carte.style.color = "red";
        carte.style.backgroundColor = "lightyellow";
    });
}
```

- `document.getElementById("titre")` : trouve un élément par son **id**.
- `document.querySelector(".carte")` : trouve **seulement le premier** élément de cette classe.
- `document.querySelectorAll(".carte")` : trouve **tous** les éléments correspondants.
- `.forEach(...)` : répète une action pour chacun des éléments trouvés.

Le point `.` signifie « classe », comme en CSS. On peut aussi écrire `document.querySelectorAll("p.carte")` pour sélectionner seulement les paragraphes de classe `carte`.

**Autre possibilité :** `document.getElementsByClassName("carte")` récupère également les éléments de cette classe, mais renvoie une collection différente, sur laquelle `forEach()` ne fonctionne pas directement.

### 🎯 À essayer

Ajoute une quatrième carte et vérifie qu'elle change de couleur aussi. Puis crée un bouton qui modifie **uniquement la première** carte avec `querySelector()`.

## 6. Afficher et cacher un élément 👀

Dans `index.html` :

```html
<p id="secret">🎉 Tu as trouvé le message secret !</p>

<button onclick="cacher()">
    Cacher
</button>

<button onclick="afficher()">
    Afficher
</button>
```

Dans `script.js` :

```javascript
function cacher() {
    document.getElementById("secret").style.display = "none";
}

function afficher() {
    document.getElementById("secret").style.display = "block";
}
```

`display = "none"` cache un élément.

`display = "block"` le rend visible sous forme de bloc.

### 🎯 À essayer

Crée un bouton qui permet de cacher une image de ton site !

## 7. Les variables : mémoriser des informations 📦

Une variable permet de conserver une valeur.

```javascript
let score = 0;

score = score + 1;
score = score + 1;

console.log(score); // Affiche 2
```

`let` permet de créer une variable.

`console.log()` affiche des informations dans la console du navigateur (accessible avec **F12**).

On peut aussi stocker du texte :

```javascript
let prenom = "Alex";
let message = "Bonjour " + prenom;

console.log(message);
```

## 8. Créer un compteur 🔢

Voici un exemple qui combine variables, fonctions et HTML.

Dans `index.html` :

```html
<h2 id="score">0</h2>

<button onclick="ajouterPoint()">
    +1 point !
</button>
```

Dans `script.js` :

```javascript
let score = 0;

function ajouterPoint() {
    score = score + 1;
    document.getElementById("score").textContent = score;
}
```

À chaque clic, le score augmente !

### 🎯 À essayer

Ajoute un bouton qui remet le score à zéro.

## 9. Bonus : les conditions 🤔

Une condition permet à JavaScript de prendre une décision.

```javascript
let score = 12;

if (score >= 10) {
    alert("Bravo, tu as gagné !");
} else {
    alert("Continue à jouer !");
}
```

`if` signifie « si ».

`else` signifie « sinon ».

Tu peux utiliser des conditions pour créer un quiz, vérifier un mot de passe fictif ou décider du gagnant d'un jeu.

## 10. Bonus : les nombres aléatoires 🎲

Pour choisir un nombre au hasard entre 1 et 6 :

```javascript
let nombre = Math.floor(Math.random() * 6) + 1;

alert("Tu as obtenu : " + nombre);
```

Tu peux utiliser ce code pour créer un dé virtuel, un tirage au sort ou un petit jeu.

## 11. Bonus : dessiner dans un Canvas 🎨

Un `<canvas>` est une zone de dessin dans la page HTML. JavaScript peut y dessiner des formes et les déplacer. Contrairement à un élément HTML classique, il faut **redessiner** le canvas quand le personnage bouge.

Dans `index.html` :

```html
<canvas id="jeu" width="600" height="300" tabindex="0"></canvas>
<p>Clique sur le canvas, puis utilise les flèches du clavier !</p>
```

Dans `style.css` :

```css
#jeu {
    border: 2px solid black;
    background: #e8f4ff;
    max-width: 100%;
}
#jeu:focus { outline: 3px solid orange; }
```

Dans `script.js` :

```javascript
const canvas = document.getElementById("jeu");
const ctx = canvas.getContext("2d");

let x = 100;
let y = 100;
const taille = 35;
const vitesse = 4;
const touches = new Set();

canvas.addEventListener("keydown", function(event) {
    if (["ArrowUp", "ArrowDown", "ArrowLeft", "ArrowRight"].includes(event.key)) {
        event.preventDefault(); // Empêche les flèches de faire défiler la page
        touches.add(event.key);
    }
});

canvas.addEventListener("keyup", function(event) {
    touches.delete(event.key);
});

canvas.addEventListener("blur", function() {
    touches.clear();
});

function animer() {
    if (touches.has("ArrowLeft")) x -= vitesse;
    if (touches.has("ArrowRight")) x += vitesse;
    if (touches.has("ArrowUp")) y -= vitesse;
    if (touches.has("ArrowDown")) y += vitesse;

    // Garder le personnage à l'intérieur du canvas
    x = Math.max(0, Math.min(canvas.width - taille, x));
    y = Math.max(0, Math.min(canvas.height - taille, y));

    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = "tomato";
    ctx.fillRect(x, y, taille, taille);

    requestAnimationFrame(animer);
}

requestAnimationFrame(animer);
```

**Comment ça fonctionne ?**

- `getContext("2d")` permet de dessiner sur le canvas.
- `fillRect(x, y, largeur, hauteur)` dessine un rectangle : ici, notre personnage.
- `clearRect(...)` efface l'image précédente avant de redessiner.
- `keydown` et `keyup` détectent les touches enfoncées et relâchées.
- `requestAnimationFrame(animer)` relance le dessin à chaque image pour obtenir une animation fluide.
- `tabindex="0"` permet au canvas de recevoir le clavier après un clic.

**Important dans la présentation Reveal.js :** clique d'abord sur le canvas interactif pour lui donner le focus. Les flèches servent alors à déplacer le personnage, pas à changer de slide. Clique ailleurs pour reprendre la navigation de la présentation.

### 🎯 À essayer

Change la taille, la couleur ou la vitesse du personnage. Dessine un deuxième rectangle comme obstacle, ou remplace le rectangle par un cercle avec `ctx.arc()` !

## 🚀 À toi de jouer : améliore ton projet !

Tu n'as pas besoin de recommencer ton site. Continue simplement ton projet HTML/CSS et ajoute les interactions qui t'intéressent.

Voici quelques idées :

| Idée | Difficulté |
|---|---|
| Bouton qui affiche un message | ⭐ |
| Bouton qui change la couleur du site | ⭐ |
| Afficher ou cacher une image | ⭐ |
| Compteur de clics | ⭐⭐ |
| Mode sombre / mode clair | ⭐⭐ |
| Quiz avec plusieurs réponses | ⭐⭐⭐ |
| Jeu du nombre mystère | ⭐⭐⭐ |
| Pierre, feuille, ciseaux | ⭐⭐⭐ |
| Personnage qui bouge dans un Canvas | ⭐⭐⭐ |

Tu peux aussi inventer ta propre interaction !

## 🛠️ Un problème dans ton code ?

Si quelque chose ne fonctionne pas :

1. Ouvre la console du navigateur avec **F12**.
2. Vérifie les messages d'erreur.
3. Vérifie que `script.js` est bien connecté à ton HTML.
4. Vérifie que les noms de tes fonctions, tes `id` et tes `class` correspondent.
5. Demande de l'aide si tu es bloqué !

**Le plus important : expérimente, teste tes idées et amuse-toi !** 🎉
