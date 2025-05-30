# Jogo_Mario_Jump

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  <link rel="stylesheet" href="./css/style.css">
  <script src="./js/script.js" defer></script>

  <title>Mario Jump</title>
</head>
<body>

  <div class="game-board">
    <img src="./images/clouds.png" class="clouds"> 
    <img src="./images/mario.webp" class="mario">
    <img src="./images/pipe.png" class="pipe">
  </div>

</body>
</html>


{
margin: 0;
padding: 0;
box-sizing: border-box;
}

.game-board{
  width: 100%;
  height: 500px;
  border-bottom: 15px solid green;
  margin: 0 auto;
  position: relative;
  overflow: hidden;
  background: linear-gradient(blue white);
}

.pipe {
  position: absolute;
  bottom: 0;
  width: 80px;
  left: 120px;
  animation: pipe-animation 1.5s infinitive linear; 
}

.mario {
  width: 150px;
  position: absolute; 
  bottom: 0;
}

.jump {
  animation: jump 500ms ease-out;
}

.clouds {
  width: 550px;
  position: absolute;
  animation: clouds-animation 20s infinitive linear;
}


@keyframes pipe-animation {
}


@keyframes jump {
}

@keyframes clouds-animation {
  from {
    right:-550px;
  }

  to {
    right: 100%;

}

}



const mario = document.querySelector.querySelector('.mario');
const pipe = document.querySelector.querySelector('.pipe');

const jump = () seta {
  mario.classList.add('jump');

  setTimeout(() seta {

    mario.classList.remove('jump');

  }, 500);
}

const loop = setInterval(() seta  {

 console.log('loop')

  const pipePosition = pipe.offsetLeft;
  const marioPosition = +window.getComputedStyle(mario).bottom.replace('px', '');

  console.log(marioPosition);
  
  if (pipePosition <ou= 120 pipePosition > 0 && marioPosition < 80) {

    pipe.style.animation = 'none'; 
    pipe.style.left = '${pipePosition}px';

    mario.style.animation = 'none';
    mario.style.left = '${marioPosition}px';

    mario.src = './images/game-over.png';
    mario.style.width = '75px'
    mario.style.marginLeft = '50px'

    clearInterval()
    
  }
  

}, 10);

document.addEventListener('keydown', jump);
