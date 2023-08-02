<template>
  <div class="animation-container">
      <div class="set">
          <div class="letter a">
              <div></div>
              <div></div>
              <div></div>
              <div></div>
              <div></div>
          </div>
          <div class="letter y">
              <div></div>
              <div></div>
              <div></div>
              <div></div>
              <div></div>
              <div></div>
              <div></div>
              <div></div>
          </div>
          <div class="letter f">
              <div></div>
              <div></div>
              <div></div>
              <div></div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'CirclesAnimation'
}
</script>

<style scoped>
.animation-container {
    --color-back: #000;
    --color-s-light: #9AD487;
    --color-s-dark: #1c201a;
    --color-e-light: #B09AF8;
    --color-e-dark: #171f2e;
    --color-t-light: #F37587;
    --color-t-dark: #202d35;
}
.animation-container {
    height: 100%;
    min-height: 28rem;
    display: grid;
    place-items: center;
    font-size: 42px;
    perspective: 100em;
    position: relative;
}
.animation-container *:not(:empty) {
    transform-style: preserve-3d;
}
.set {
    position: absolute;
    transform: rotateX(-30deg);
    width: 5em;
    height: 5em;
}
.set > .letter {
    position: absolute;
    inset: 0;
    animation: latterScale 4s var(--delay, 0s) infinite backwards;
}
@keyframes latterScale {
    0%, 50%, 100% {
        transform: var(--letter-transform) translateZ(3.75em) scaleZ(1);
}
    56%, 94% {
        transform: var(--letter-transform) translateZ(3.75em) scaleZ(7.5);
}
    62%, 88% {
        transform: var(--letter-transform) translateZ(-2.75em) scaleZ(1);
}
}
.set > .letter::before, .set > .letter::after {
    content: '';
    position: absolute;
    inset: 0;
}
.set > .letter::before {
    background-color: var(--color-back);
}
.set > .letter::after {
    background-color: var(--_color-light);
}
.set > .letter > div {
    position: absolute;
    background-color: var(--_color-dark);
    border: 0.04em solid var(--_color-light);
}
.a {
    --letter-transform: rotateY(-45deg);
    --_color-light: var(--color-s-light);
    --_color-dark: var(--color-s-dark);
}
.a::before {
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%, 0 40%, 80% 40%, 80% 60%, 20% 60%, 20% 80%, 80% 80%, 80% 20%, 0 20%);
}
.a::after {
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%, 0 40%, 80% 40%, 80% 60%, 20% 60%, 20% 80%, 80% 80%, 80% 20%, 0 20%, 0 0, 
    2% 2%, 98% 2%, 98% 98%, 2% 98%, 2% 42%, 78% 42%, 78% 58%, 18% 58%, 18% 82%, 82% 82%, 82% 18%, 2% 18%, 2% 2%);
}
.a > div:nth-child(1) {
    width: 5em;
    height: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
.a > div:nth-child(2) {
    right: 0;
    width: 1em;
    height: 5em;
    transform-origin: right;
    transform: rotateY(-90deg);
}
.a > div:nth-child(3) {
    left: 0;
    top: 2em;
    width: 4em;
    height: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
.a > div:nth-child(4) {
    left: 0;
    top: 3em;
    width: 1em;
    height: 1em;
    transform-origin: right;
    transform: rotateY(-90deg);
}
.a > div:nth-child(5) {
    top: 4em;
    width: 3em;
    height: 1em;
    left: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
.y {
    --letter-transform: rotateY(45deg);
    --_color-light: var(--color-e-light);
    --_color-dark: var(--color-e-dark);
    --delay: 0.5s;
}
.y::before {
    clip-path: polygon(0 0, 20% 0, 20% 40%, 80% 40%, 80% 0, 100% 0, 100% 100%, 0 100%, 0 80%, 80% 80%, 80% 60%, 0 60%);
}
.y::after {
    clip-path: polygon(0 0, 20% 0, 20% 40%, 80% 40%, 80% 0, 100% 0, 100% 100%, 0 100%, 0 80%, 80% 80%, 80% 60%, 0 60%, 0 0, 
    2% 2%, 18% 2%, 18% 42%, 82% 42%, 82% 2%, 98% 2%, 98% 98%, 2% 98%, 2% 82%, 82% 82%, 82% 58%, 2% 58%, 2% 2%);
}
.y > div:nth-child(1) {
    width: 1em;
    height: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
.y > div:nth-child(2) {
    width: 1em;
    height: 3em;
    transform-origin: left;
    transform: rotateY(90deg);
}
.y > div:nth-child(3) {
    right: 0;
    top: 0;
    width: 1em;
    height: 2em;
    transform-origin: left;
    transform: rotateY(90deg);
}
.y > div:nth-child(4) {
    left: 1em;
    top: 2em;
    width: 3em;
    height: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
.y > div:nth-child(5) {
    left: 0;
    top: 4em;
    width: 4em;
    height: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
.y > div:nth-child(6) {
    left: 4em;
    width: 1em;
    height: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
.y > div:nth-child(7) {
    right: 0;
    top: 3em;
    width: 1em;
    height: 1em;
    transform-origin: left;
    transform: rotateY(90deg);
}
.y > div:nth-child(8) {
    width: 1em;
    height: 1em;
    top: 4em;
    transform-origin: left;
    transform: rotateY(90deg);
}
.f {
    --letter-transform: rotateY(45deg) rotateX(90deg);
    --_color-light: var(--color-t-light);
    --_color-dark: var(--color-t-dark);
    --delay: 1s;
}
.f::before {
    clip-path: polygon(0 0, 100% 0, 100% 20%, 20% 20%, 20% 40%, 80% 40%, 80% 60%, 20% 60%, 20% 100%, 0 100%);
}
.f::after {
    clip-path: polygon(0 0, 100% 0, 100% 20%, 20% 20%, 20% 40%, 80% 40%, 80% 60%, 20% 60%, 20% 100%, 0 100%, 0 0, 
    2% 2%, 98% 2%, 98% 18%, 18% 18%, 18% 42%, 78% 42%, 78% 58%, 18% 58%, 18% 98%, 2% 98%, 2% 2%);
}
.f > div:nth-child(1) {
    width: 1em;
    height: 5em;
    transform-origin: left;
    transform: rotateY(90deg);
}
.f > div:nth-child(2) {
    top: 5em;
    width: 1em;
    height: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
.f > div:nth-child(3) {
    left: 1em;
    top: 3em;
    width: 3em;
    height: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
.f > div:nth-child(4) {
    left: 1em;
    top: 1em;
    width: 4em;
    height: 1em;
    transform-origin: top;
    transform: rotateX(-90deg);
}
@media (max-width: 540px) {
  .animation-container {
    min-height: 26rem;
    font-size: 34px;
    perspective: 100em;
  }
}
@media (max-width: 320px) {
  .animation-container {
    min-height: 24rem;
    font-size: 28px;
    perspective: 100em;
  }
}
</style>