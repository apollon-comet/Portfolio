<template>
  <main>
    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" />
      </transition>
    </router-view>
    <AppFooter />
    <MyButton class="menu-call-btn" @click="showMenu" title="Open Menu">
      <img
        src="../assets/img/icons/menu.png"
        class="call-btn-img"
        alt="open menu"
      />
    </MyButton>
    <MyButton class="scroll-up-btn" @click="scrollToTop" title="Up">
      <img
        src="../assets/img/icons/toleft.png"
        class="call-btn-img"
        alt="to top"
      />
    </MyButton>
    <MyButton class="modal-call-btn" @click="showDialog" title="Get in touch">
      <img
        src="../assets/img/icons/edit.png"
        class="call-btn-img"
        alt="chat me"
      />
    </MyButton>
  </main>
</template>

<script>
import AppFooter from "@/components/AppFooter";
import MyButton from "@/components/UI/MyButton";

export default {
  name: "MainWrapper",
  components: {
    MyButton,
    AppFooter,
  },
  methods: {
    showMenu() {
      document.querySelector(".navbar.mobile").style.left = 0;
    },
    scrollToTop() {
      document.querySelector("main").scrollIntoView({ behavior: "smooth" });
    },
    showDialog() {
      this.$emit("showDialog");
    },
  },
  mounted() {
    window.addEventListener("scroll", function () {
      document
        .querySelector(".scroll-up-btn")
        .classList.toggle("visible", window.scrollY > 600);
      document
        .querySelector(".btns-wrapper")
        .classList.toggle("extended", window.scrollY > 600);
    });
  },
};
</script>

<style>
main {
  padding: 0 0 0 var(--navbar-width);
  position: relative;
  z-index: 3;
}
section {
  padding: 2rem 1rem;
  min-height: 90vh;
}
.container {
  width: 90%;
  max-width: 1100px;
  margin: 0 auto;
}
.section-heading {
  font-weight: 800;
  font-size: 7rem;
  color: var(--regular-text-color);
  text-shadow: var(--section-heading-shadow);
  margin-bottom: 2rem;
}
.section-text {
  padding: 2rem;
  background-color: var(--section-text-bg);
  backdrop-filter: blur(5px);
  border-radius: var(--box-border-radius);
  border: var(--box-border);
  box-shadow: var(--box-shadow);
  color: var(--regular-text-color);
  font-size: 20px;
  line-height: 160%;
  font-weight: 400;
  letter-spacing: 0.5px;
  margin-bottom: 1rem;
  transition: opacity 0.2s ease;
  background-image: url(../assets/img/Noise.png);
}
.section-text strong {
  color: var(--default-text-color);
  font-weight: inherit;
  font-size: 80%;
  letter-spacing: 1px;
}
.section-heading::selection,
.section-text::selection {
  background: var(--navbar-bg-color);
}
/*==== ROUTER TRANSITION ==========*/
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease-out;
}
@media (max-width: 991.98px) {
  .section-heading {
    font-size: 5rem;
  }
}
@media (max-width: 600px) {
  main {
    padding-left: 0;
  }
  .section-heading {
    font-size: 3rem;
  }
  .section-text {
    padding: 1rem;
    font-size: 17px;
  }
  .menu-call-btn {
    display: grid;
    width: 3rem;
    height: 3rem;
  }
  .menu-close-btn {
    display: grid;
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
    right: 0.6rem;
    width: 3.8rem;
    height: 3.8rem;
    background-color: rgba(100, 100, 100, 0.4);
  }
  .btns-wrapper.extended {
    height: 7.6rem;
  }
}
</style>
