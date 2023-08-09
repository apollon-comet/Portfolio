<template>
  <div class="navbar" v-motion-slide-left>
    <div class="navbar-intro">
      <div class="navbar-intro-avatar"></div>
      <h2 class="navbar-intro-name">Victor Knight</h2>
      <h3 class="navbar-intro-position">AI & ML, Full-stack</h3>
    </div>
    <div id="nav" class="nav-menu">
      <router-link
        v-for="navlink in navlinks"
        :key="navlink.link"
        :to="navlink.link"
      >
        <img
          :src="require('../assets/img/icons/' + navlink.img)"
          width="20"
          height="20"
          class="navlink-icon"
          :alt="navlink.name"
          loading="lazy"
        />
        <span class="navlink-text" :style="navlink.color">{{
          navlink.name
        }}</span>
        <div
          class="arrow-right-figure"
          :style="`background-${navlink.color}`"
        ></div>
      </router-link>
    </div>
    <ThemeSwitcher />
  </div>
</template>

<script>
import ThemeSwitcher from "@/components/UI/ThemeSwitcher.vue";

export default {
  name: "NavBar",
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
  methods: {},
};
</script>

<style>
.navbar {
  width: var(--navbar-width);
  min-width: 8rem;
  padding: 1rem;
  color: #fff;
  height: 300px;
  min-height: 100vh;
  overflow: auto;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 5;
  transition: 0.5s;
}
.navbar-intro {
  height: 19rem;
  padding: 1rem;
  background-color: #cfdbf9;
  background-image: url(../assets/img/Noise.png),
    radial-gradient(circle farthest-corner at 100% 0%, #715fa5, #ada4c4);
  background-position: 0px 0px, 0px 0px;
  background-size: 400px, auto;
  background-repeat: repeat, repeat;
  border-radius: var(--box-border-radius);
  border: var(--box-border);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-shadow: var(--box-shadow);
}
.navbar-intro-avatar {
  width: 9rem;
  height: 9rem;
  aspect-ratio: 1/1;
  border-radius: 50%;
  border: 5px solid var(--home-color);
  background: url(../assets/img/5.jpg) 0 0 no-repeat;
  background-size: cover;
}
.navbar-intro-name {
  letter-spacing: 1px;
  font-size: 1.8rem;
  text-align: center;
  line-height: 110%;
  margin: 0.5rem 0;
  text-shadow: 0 0 32px 0 rgb(0 0 0 / 60%);
}
.navbar-intro-position {
  letter-spacing: 1px;
  color: var(--contact-color);
  text-align: center;
  line-height: 110%;
  text-shadow: 0 0 32px 0 rgb(0 0 0 / 60%);
}
.nav-menu a {
  display: flex;
  align-items: center;
  width: 80%;
  padding: 1.2rem 10%;
  letter-spacing: 0.5px;
  color: var(--default-text-color);
  text-shadow: var(--regular-text-shadow);
  background-color: var(--nav-item-bg);
  background-image: url(../assets/img/Noise.png);
  border-radius: var(--box-border-radius);
  border: var(--box-border);
  margin: 0 auto 0.7rem auto;
  position: relative;
  z-index: 7;
  top: -1.5rem;
  box-shadow: var(--box-shadow);
  text-decoration: none;
  overflow: hidden;
  transition: all ease 0.2s;
}
.nav-menu a:hover {
  background-color: var(--nav-item-hover-bg);
}
.nav-menu a.link-home {
  color: var(--home-color);
  text-shadow: 0 0 6px var(--home-color);
}
.nav-menu a.link-home:hover {
  text-shadow: 0 0 6px var(--home-color);
}
.nav-menu a.link-about {
  color: var(--about-color);
}
.nav-menu a.link-projects {
  color: var(--projects-color);
}
.nav-menu a.link-contact {
  color: var(--contact-color);
}
.nav-menu a .navlink-icon {
  margin-right: 1rem;
  filter: drop-shadow(var(--regular-text-shadow));
  transition: all ease 0.2s;
}
.navlink-text {
  transition: all ease 0.3s;
}
.arrow-right-figure {
  width: 0.6rem;
  min-width: 0.6rem;
  height: 0.8rem;
  clip-path: polygon(40% 0, 100% 50%, 40% 100%, 30% 85%, 70% 50%, 30% 15%);
  margin-left: 2rem;
  opacity: 0;
  border: var(--box-border);
  transition: all ease 0.4s;
}
.nav-menu a:hover .navlink-icon {
  transform: translateX(-4rem);
  opacity: 0;
}
.nav-menu a:hover .navlink-text {
  transform: translateX(-1rem);
}
.nav-menu a:hover .arrow-right-figure {
  opacity: 1;
  transform: translateX(-2rem);
}
@media (max-width: 1100px) {
  .navbar-intro-avatar {
    width: 7rem;
    height: 7rem;
  }
  .navlink-text {
    display: none;
  }
  .nav-menu a {
    justify-content: center;
  }
  .nav-menu a:hover .navlink-icon {
    transform: translateX(0);
    opacity: 1;
  }
  .nav-menu a .navlink-icon {
    margin-right: 0;
  }
  .arrow-right-figure {
    display: none;
  }
}
@media (max-width: 840px) {
  .navbar-intro-avatar {
    width: 6rem;
    height: 6rem;
  }
  .navbar-intro-name {
    font-size: 1.2rem;
  }
}
@media (max-width: 600px) {
  .navbar {
    display: none;
  }
}
</style>
