<template>
  <div class="my-modal" @click.stop="hideDialog">
        <div @click.stop class="my-modal-content">
          <div class="container">
            <h3 class="modal-heading">Get in touch</h3>
            <slot></slot>
          </div>
        </div>
      </div>
</template>

<script>
export default {
    name: 'MyModal',
    methods: {
        hideDialog() {
            this.$emit('hideDialog')
        }
    }
}
</script>

<style>
.my-modal {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgba(0,0,0,.7);
    backdrop-filter: blur(8px);
    opacity: 0;
    z-index: -5;
    transition: .2s;
}
.my-modal.active {
    opacity: 1;
    z-index: 5;
}
.my-modal-content {
    width: 90%;
    max-width: 600px;
    border-radius: var(--box-border-radius);
    background-color: rgba(255,255,255,.25);
    padding: 1rem;
    min-height: 10rem;
    box-shadow: 0 0 32px 0 rgb(0 0 0 / 40%);
    background-image: url(../../assets/img/Noise.png);
}
.modal-heading {
  font-weight: 300;
  text-align: center;
  text-transform: uppercase;
  font-size: 2rem;
  letter-spacing: 1px;
  text-shadow: 0 0 32px 0 rgb(0 0 0 / 60%);
  margin-bottom: 1rem;
}
.my-modal-content .contact-wrapper-column {
  width: 100%;
}
</style>