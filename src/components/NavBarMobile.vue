<template>
  <div class="navbar mobile" @click="closeMenu">
    <div class="navbar-content" @click.stop>
      <button class="btn menu-close-btn" @click="closeMenu">
        <img
          src="../assets/img/icons/toleft.png"
          class="call-btn-img"
          alt="close menu"
        />
      </button>
      <div class="navbar-intro">
        <div class="navbar-intro-avatar"></div>
        <h3 class="navbar-intro-name">Victor Knight</h3>
        <p class="navbar-intro-position">Full-stack Developer</p>
      </div>
      <div id="nav" class="nav-menu">
        <router-link
          v-for="navlink in navlinks"
          :key="navlink.link"
          :to="navlink.link"
          @click="closeMenu"
        >
          <img
            :src="require('../assets/img/icons/' + navlink.img)"
            class="navlink-icon-mob"
            width="18"
            height="18"
            :alt="navlink.name"
            loading="lazy"
          />
          <span class="navlink-text" :style="navlink.color">{{
            navlink.name
          }}</span>
        </router-link>
      </div>
      <ThemeSwitcher />
    </div>
  </div>
</template>

<script>
import ThemeSwitcher from "@/components/UI/ThemeSwitcher.vue";

export default {
  name: "NavBarMobile",
  components: {
    ThemeSwitcher,
  },
  data() {
    return {
      navlinks: [
        {
          name: "Home",
          link: "/",
          color: "color:var(--home-color)",
          img: "homepage.png",
        },
        {
          name: "About",
          link: "/about",
          color: "color:var(--about-color)",
          img: "info.png",
        },
        {
          name: "Projects",
          link: "/projects",
          color: "color:var(--projects-color)",
          img: "coding.png",
        },
        {
          name: "Contact",
          link: "/contact",
          color: "color:var(--contact-color)",
          img: "chat.png",
        },
      ],
    };
  },
  methods: {
    closeMenu() {
      document.querySelector(".navbar.mobile").style.left = "-100%";
    },
  },
};
</script>

<style>
.navbar.mobile {
  display: none;
}
@media (max-width: 600px) {
  .navbar.mobile {
    display: block;
    left: -100%;
    top: 0;
    width: 100%;
    height: auto;
    min-height: 100vh;
    max-height: 19rem;
    overflow-y: scroll;
    padding: 0;
  }
  .navbar.mobile .navbar-content {
    width: 75%;
    min-height: 100vh;
    padding: 2rem 1.5rem;
    backdrop-filter: blur(6px);
    box-shadow: var(--box-shadow);
    background-color: var(--navbar-mobile-bg-color);
    border-right: var(--box-border);
  }
  .navbar.mobile .navbar-intro-avatar {
    width: 9rem;
    height: 9rem;
  }
  .navbar.mobile .nav-menu a {
    justify-content: flex-start;
  }
  .navlink-icon-mob {
    margin-right: 1rem;
  }
  .navbar.mobile .navlink-text {
    display: inline-block;
  }
}
@media (max-width: 350px) {
  .navbar.mobile .navbar-intro {
    height: 16rem;
  }
  .navbar.mobile .navbar-intro-avatar {
    width: 6rem;
    height: 6rem;
  }
  .navbar.mobile .nav-menu a {
    padding: 0.8rem 10%;
  }
}
</style>
