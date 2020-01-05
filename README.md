# **Bonnes pratiques en programmation**

Bonjour à tous,
J'espère que l'entraide du jour à pu se mettre en place sans trop de complications. 
J'aimerais partager un certain nombres de choses à garder dans l'attention qui permettront peut-être d'avoir plus de clarté dans l'élaboration des codes à produire. Bonne lecture :clin_d'œil:

## Le nommage

### **_Choisir une seule langue_** 

Puisque notre environnement de travail est en anglais mais que nous réfléchissons davantage en français il arrivera bien souvent que les variables, fonctions et tout autres éléments soit nommé tantôt en anglais, tantôt en français. Etant donné que les langages de programmation sont en anglais , mieux vaut favoriser l'anglais pour le nommage des éléments que nous créerons. De plus il s'avère que l'anglais demande bien souvent moins de mots pour décrire la même chose.

>`"obtenir la valeur du dé" vs. 
>"get dice value"`

>`"définir la position de l'arrière-plan " vs. "set background position"`

### **_Les variables_** :open_file_folder:  :arrow_left:

 Une variable représente généralement une donnée, un élément constitutif d'un ensemble plus complexe. Nous venons de constater la multiplicité des variables nécessaires à l'élaboration d'un programme (même simple e.g. : un lancé de dés). Il est important d'être le plus précis possible quant à leur nomination.
  
Si je souhaite stocker la valeur d'un dé :

```js
var d = getDiceValue();  // Pas très parlant ...
var monDe = getDiceValue();  // Oui, mais quoi exactement, sa forme, son aspect, son affichage, sa valeur ? 
var diceValue = getDiceValue();  // intention plus claire de stocker la valeur du dé
```

### **_Les fonctions_** :gear: :wrench:

 Une "fonction" comme son nom l'indique est là pour remplir un rôle particulier, pour effectuer une action particulière ainsi on lui préférera un nom en relation avec cette action (maximum 5 mots).

```js
// Peu descriptif 
function chiffreDuDe() {
    // instructions
}

// Exemple descriptif de l'action de la fonction
function obtenirLaValeurDunDe() {
    // instructions
}

// En anglais 
function getDiceValue() {
    // instructions
}
```

Les fonctions de types `getQuelqueChose` et `setQuelqueChose` sont très fréquemment utilisées :
>- `getQuelqueChose` : pour obtenir une valeur (textuelle, numérique, booléenne, etc ...)
>- `setQuelqueChose` : pour définir une valeur (textuelle, numérique, booléenne, etc ...)
  
Il peut s'avérer bien utile de s'y habituer dès maintenant.


## Organisation du code

### **_Les commentaires_** :raised_hand: :speech_balloon:

Il ne faut surtout pas sous-estimer l'importance des commentaires. Bien sûr l'interpréteur ne les lira pas mais ils seront indispensables pour une bonne compréhension globale comme spécifique durant l'élaboration du code et plus tard pour sa maintenance.

```javascript
// En JS ceci "//" commente une seule ligne

/* 
    Et ceux la commentent plusieurs lignes à la fois
    Ici aussi par exemple 
    Toujours pas de code .... 
*/

```

>Il existe une extension de *VSCode* *VSCodium* qui permet la coloration du code par des signe un peu particulier `//` ,`//?` , `//!` , et bien d'autres. Il vous faudra installer ou vérifier l'installation de l'extension **_Better comments_**.

### **_L'indentation_** :grin: :trident:

L'indentation est capitale pour la compréhension rapide par le visuel des différents niveau d'imbrications de blocs de code : 

```js
do {
    requestedThrowsNb = parseInt(prompt("combien de lancer voulez-vous par joueur ? (6 max.)")); 
    if  (requestedThrowsNb > 6) {
        alert("Vous ne pouvez lancer que 6 dès au maximum.")
    } 
    if (requestedThrowsNb < 0) {
        alert("Sérieusement ?! ... -_-'"); 
    }
} while (requestedThrowsNb < 0 || requestedThrowsNb > 6 );```
```


>La hiérarchie code du haut est quand même plus facile à saisir que celle d'en bas et ça même s'il faut prendre le temps de comprendre son rôle.


```js
do {
requestedThrowsNb = parseInt(prompt("combien de lancer voulez-vous par joueur ? (6 max.)")); if  (requestedThrowsNb > 6) {
alert("Vous ne pouvez lancer que 6 dès au maximum.")
} 
    if (requestedThrowsNb < 0) {
    alert("Sérieusement ?! ... -_-'"); 
    }} while (requestedThrowsNb < 0 || requestedThrowsNb > 6 ); 
```

### **_Ranger pour s'y retrouver_** :twisted_rightwards_arrows: :bento: 

 Organiser son code c'est comme faire à manger, on y gagne à s'organiser, surtout quand qu'on est pas encore habitué, voici un exemple parmi d'autres plus bas :

```js 
/** LOCAL FUNCTIONS  **/

function getDiceValue() {
    // instructions
}
function getDicePosition() {
    // instructions
}
function rollDice() {
    // instructions
}
/** MAIN PROGRAM **/

// Variables declaration

// Instructions with function calls 

/** END OF MAIN PROGAM **/
```

### **_Documenter son code_** :nerd::+1: :couleur_de_peau-3: 
Documenter les grandes étapes nécessaires à l'exécution du code est une bonne habitude à prendre, cela est aussi vrai à plus petites échelles, avec les variables et les fonctions.

```js
function moveDice(dice) {
    /* afficher la valeur d'un dé en fonction de sa valeur */
    var newPosition = -1 * dice * 100 + 100;
    return newPosition + "px"; // nouvelle position du background convertie en pixels
}
```

### **_S'assurer que la logique tient la route_** :traffic_light: :car:

Lorsque l'on plonge dans les méandres d'un exercice à coder, c'est précisément comme rentrer dans le détails d'un sujet de conversation ou de présentation.  Parfois la direction globale dans laquelle on souhaite aller nous échappe et notre réflexion dérive.

Il est important d'un part de bien comprendre où l'on veut aller mais aussi savoir revenir en arrière pour être sûr que toutes les lignes de code tiennent la route.

Cela revient à traduire en français le comportement des différents blocs de code que l'on écrit. Et pourquoi ne pas l'expliquer à son canard en plastique favori ?! :clin_d'œil:

![rubberducker](https://www.gravatar.com/avatar/cb86fc582df8ea9a99ef2b3f1ac4e99e?s=328&d=identicon&r=PG)

J'espère que ces conseils, venus de ma modeste expérience de la programmation vous seront utiles. Ils sont bien entendu susceptibles d'être complétés et corrigés si besoin.

Restons solidaires et disponibles autant que possible pour évoluer.
Bien à vous tous et à demain.
