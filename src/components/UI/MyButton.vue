<template>
  <button class="btn">
      <slot></slot>
  </button>
</template>

<script>
export default {
    name: 'MyButton'
}
</script>

<style>
.btn {
    padding: 1rem 2rem;
    background-color: var(--primary-btn-color);
    border-radius: 4px;
    color: #fff;
    font-size: inherit;
    border: none;
    cursor: pointer;
    transition: all .2s ease;
    font-family: inherit;
    box-shadow: var(--box-shadow);
}
.btn:active {
    transform: scale(0.98);
}
.btn a {
  display: flex;
  width: 100%;
  height: 100%;
  align-items: center;
  justify-content: center;
}
.menu-call-btn {
  background-color: var(--about-color);
  position: fixed;
  z-index: 3;
  top: 1.2rem;
  left: 1rem;
  border-radius: 50%;
  border: var(--box-border);
  width: 3.2rem;
  height: 3.2rem;
  padding: 0;
  display: none;
  place-items: center center;
  background-image: url(../../assets/img/Noise.png);
}
.menu-call-btn .call-btn-img {
  width: 1.6rem;
  height: 1.6rem
}
.menu-close-btn {
  background-color: var(--projects-color);
  position: absolute;
  top: 1rem;
  right: .5rem;
  border-radius: 50%;
  border: var(--box-border);
  width: 3.2rem;
  height: 3.2rem;
  padding: 0;
  display: none;
  place-items: center center;
  background-image: url(../../assets/img/Noise.png);
}
.menu-close-btn .call-btn-img {
  width: 2rem;
  height: 2rem;
  margin-right: 0.3rem;
}
.btns-wrapper {
  position: fixed;
  z-index: 30;
  bottom: 1.4rem;
  right: 1.4rem;
  border-radius: 100px;
  width: 4rem;
  height: 4rem;
  background-color: rgba(150, 150, 150, .4);
  backdrop-filter: blur(5px);
  border: var(--box-border);
  transition: .5s
}
.btns-wrapper.extended {
  height: 7.8rem;
}
.modal-call-btn,
.scroll-up-btn {
  position: fixed;
  bottom: 1.8rem;
  right: 1.8rem;
  border-radius: 50%;
  border: var(--box-border);
  width: 3.2rem;
  height: 3.2rem;
  padding: 0;
  display: grid;
  place-items: center center;
  background-image: url(../../assets/img/Noise.png);
  transition: .5s
}
.modal-call-btn .call-btn-img {
  width: 1.5rem;
  height: 1.5rem
}
.modal-call-btn {
  z-index: 33;
}
.scroll-up-btn {
  z-index: 32;
  background-color: var(--blue);
}
.scroll-up-btn img {
  width: 1.8rem;
  height: 1.8rem;
  transform: rotateZ(90deg)
}
.scroll-up-btn.visible {
  bottom: 5.6rem;
}
@media (max-width: 600px) {
    .menu-call-btn {
      display: grid;
      width: 3rem;
      height: 3rem;
    }
    .menu-close-btn {
      display: grid
    }
    .modal-call-btn,
    .scroll-up-btn {
      bottom: 1.4rem;
      right: 1rem;
      width: 3rem;
      height: 3rem;
    }
    .scroll-up-btn.visible {
      bottom: 5.2rem;
    }
    .btns-wrapper {
      bottom: 1rem;
      right: .6rem;
      width: 3.8rem;
      height: 3.8rem;
      background-color: rgba(100, 100, 100, .4);
    }
    .btns-wrapper.extended {
      height: 7.6rem;
    }
}
</style>
