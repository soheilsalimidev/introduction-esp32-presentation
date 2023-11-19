<template>
  <div  class="slidev-layout"
        :class="{ grid: $attrs.center }">
 <CornerCurves class="absolute bottom-0 right-0 transform scale-x--100" />
    <div class="transform-3d card" id="hero-card">
        <slot/>
    </div>
    <div class="bg-container">
      <div class="box" data-variant="1"></div>
      <div class="box" data-variant="2"></div>
      <div class="box" data-variant="3"></div>
    </div>
  </div>
</template>

<style >

html{
  background: rgb(131,58,180);
  background: rgb(200,200,200);
  color: rgb(220, 220, 220);
}


.box{
  position: absolute;
  z-index: -2;
  border-radius: 1rem;
    box-shadow: 
    inset 0px 0px 0px 1px rgba(255, 255, 255, .1),
    inset 0px 0px 7px 1px rgba(255, 255, 255, .1),
    6px 6px 15px 0px rgba(0, 0 ,0, .4)
    ;
  animation-name: box-1-animation;
  animation-duration: 4s;
  animation-iteration-count: infinite;
  animation-timing-function: ease-in-out;
}

.box[data-variant="1"] {
	animation-name: box-1-animation;
	top: -25rem;
	left: -56rem;
	height: 4rem;
	width: 4rem;
	background: #2c5bf1;
}

.box[data-variant="2"] {
	animation-name: box-2-animation;
	animation-delay: -.5s;
	animation-duration: 2s;
	top: -2rem;
	left: -31rem;
	height: 3rem;
	width: 8rem;
	background: #ffa62d;
}

.box[data-variant="3"] {
	animation-name: box-3-animation;
	animation-delay: -1s;
	animation-duration: 2s;
	top: -29rem;
	right: -2rem;
	height: 9rem;
	width: 4rem;
	background: #5c2c86;
}

.transform-3d{
  transform-style: preserve-3d;
  transform:
    perspective(1000px)
    rotateY(var(--rotateY))
    rotateX(var(--rotateX));
  
  transition: transform 200ms;
}

.transform-3d:hover{  
  transition: transform 50ms;
}

.card {
  
 height: 100%;
 width: 100%;


  --border-radius: 1rem;
  --border-color: rgba(120 , 13 , 227, .2);
  
  --blur: 10px;
  
  --glow-rotation: 25deg;
  --glow-init-rotation: 180deg;
  
  --glow-color: #ff7a2daa;
  --glow-width: 35deg;
  --glow-border-width: 1px;
  
  --highlight-width: 10deg;
  --highlight-color: rgba(255, 255, 255, .5);

  
  position: relative;
  padding: 2rem;
  padding-top: .5rem;
  display: inline-block;
  border-style: solid;
  border-radius: var(--border-radius);
  border-width: 0;
  border-color: rgba(255,255,255);
  box-shadow: 
    inset 0px 0px 0px 1px rgba(255, 255, 255, .1),
    inset 0px 0px 7px 1px rgba(255, 255, 255, .1),
    0px 0px 7px 0px rgba(0, 0 ,0, .25)
    ;
  border-color: rgba(255, 255, 255, .35);
  background: linear-gradient(225deg,
    rgba(255,255,255,0.1) 0%,
    rgba(100 ,100 ,100 ,0.1) 25%,
    rgba(0  ,0  ,0  ,0.1) 50%,
    rgba(0  ,0  ,0  ,0.1) 75%,
    rgba(100 ,100 ,100 ,0.1) 100%);
  background-color: rgba(255, 255, 255, .1);
  backdrop-filter: blur(10px);
}

.card:before {
  
  content: "";
  display: inline-block;
  position: absolute;
  inset: 0;
  border-radius: inherit;
  padding-top: var(--glow-border-width, 1px);
  padding-right: var(--glow-border-width, 1px);
  -webkit-mask: linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  
  background: conic-gradient(
    from calc(var(--glow-rotation, 0deg) + var(--glow-init-rotation, 180deg)) at 50% 50%,
    var(--border-color, transparent) 0deg,
    var(--border-color, transparent) calc(180deg - var(--highlight-width, 2deg) - var(--glow-width, 2deg)),
    var(--glow-color, white) calc(180deg - var(--highlight-width, 2deg)),
    var(--highlight-color, white) 180deg,
    var(--glow-color, white) calc(180deg + var(--highlight-width, 2deg)),
    var(--border-color, transparent) calc(180deg + var(--highlight-width, 2deg) + var(--glow-width, 2deg)),
    var(--border-color, transparent) 360deg
    );
  
/*   filter: blur(0px); */
  mix-blend-mode: lighten;
}

.container{
  height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
  
  position: relative;
}

.bg-container{
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  pointer-events: none;
}

.flex{
  display: flex;
  justify-content: center;
}

@keyframes box-1-animation{
  0% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(90deg);
  }
  50% {
    transform: rotate(180deg);
  }
  75% {
    transform: rotate(270deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

@keyframes box-2-animation{
  0% {
    transform: translate(-1rem , 0rem);
  }
  50%{
    transform: translate(2rem, 0rem);
  }
  100%{
    transform: translate(-1rem, 0rem);
  }
}

@keyframes box-3-animation{
  0% {
    transform: translate(0rem , -1.5rem);
  }
  50%{
    transform: translate(0rem, .5rem);
  }
  100%{
    transform: translate(0rem, -1.5rem);
  }
}
</style>