# BeCode-Animation

## Objectifs
<p>BeCode a besoin de toi. BeCode va réaliser des vidéos tutos sur youtube pour aider les personnes à s'inscrire. On a besoin d'une petite animation de maximum 10 s pour la fin de la vidéo. Votre mission sera de faire cette animation en javascript/css !</p>

# Langages utilisés ? 
* HTML 5
* CSS 3 
* JavaScript 
* SASS

## Que contient t'il ? 
<p>Le projet contient un fichier "index.html", un script javascript, une feuille de style css/scss et des ressources graphiques (logo) permettant de réaliser l'animation.</p>

# Comment le récupérer ?
<p>Pour le récupérer, vous pouvez cloner le dépot sur votre ordinateur ou vous rendre sur le GitHub Pages.</p>

---

# Présentation du code

## Fichier HTML

```markdown
<!DOCTYPE html>
<html lang="fr">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" type="text/css" href="./assets/css/style.min.css">
    <link rel="stylesheet" type="text/css" href="./assets/css/animate.min.css">
    <title>Becode-Animation</title>
</head>

<body>
    <!-- Article -->
    <article class="imgBx">
        <img class="img1 animated bounceInDown" src="./assets/img/BeCode.svg" alt="Logo BeCode">
    </article>
    <!--  -->
    <!-- Caption -->
    <article class="caption">
        <h1 class="glitch" data-texte="&#139; In Code We Trust &#155;"><span class="text" id="str"> &#139; In Code We
                Trust &#155;</span>
            </span>
            <span class="type-cursor">|</span>
    </article>
    <!-- Caption-Fin -->
    <!-- Script JS -->
    <script src="./assets/js/script.js"></script>
    <!-- Script JS-Fin -->
</body>

</html>
<!--Made by Maxim Lopez-->
```

## Fichier CSS
``` markdown
/* PHRASE : In Code We Trust */
body {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  background-color: #F5F5DC;
  font-family: 'Ubuntu', sans-serif;
  margin: 50px;
  letter-spacing: 0px;
  font-weight: bold;
  color: #4d4d4d;
  text-shadow: 1px 1px #e2d59c, 2px 2px #e2d59c, 3px 3px #e2d59c, 4px 4px #e2d59c, 5px 5px #e2d59c, 6px 6px #e2d59c, 7px 7px #e2d59c, 8px 8px #e2d59c, 9px 9px #e2d59c, 10px 10px #e2d59c, 11px 11px #e2d59c, 12px 12px #e2d59c, 13px 13px #e2d59c, 14px 14px #e2d59c, 15px 15px #e2d59c, 16px 16px #e2d59c, 17px 17px #e2d59c, 18px 18px #e2d59c, 19px 19px #e2d59c, 20px 20px #fff1b1;
  margin: 0;
  padding: 0;
  display: flex;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  min-height: 100vh;
  overflow: hidden;
}

h1 {
  font-size: 50px;
}

.imgBx {
  position: relative;
  width: 500px;
  height: 500px;
}

.img1 {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  -webkit-transform-origin: left;
      -ms-transform-origin: left;
          transform-origin: left;
}

.type-cursor {
  color: black;
  font-size: 1em;
  -webkit-animation: blink 0.5s infinite linear;
          animation: blink 0.5s infinite linear;
}

@-webkit-keyframes blink {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes blink {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

```

## Fichier JavaScript
``` markdown
let newElement = document.querySelector("img")


function switchclass(){
    setTimeout(function(){  
        newElement.classList.remove("bounceInUp");
        newElement.classList.add("bounceOutDown");
    }, 7000);}  
switchclass();


let pos=0;
let speed=250;
let str=document.getElementById('str').innerText;

document.getElementById('str').innerHTML = ""

function type() {
    if(pos<str.length){
        document.getElementById('str').innerText += str.charAt(pos);
        pos++;
        setTimeout(type,speed);
    }else{
        setTimeout(erase,speed);
    }
}

setTimeout(type,1500)

function erase() {
    if(pos >= str.length) {
        let temp= str.substring(0,pos);
        document.getElementById('str').innerText = temp;
        pos--
        setTimeout(erase,speed);
    }
}
```