<template>
  <section class="projects-section" id="projects">
    <div class="container">
      <h2 class="section-heading delay-2">My Projects</h2>
      <MySelect
        :options="options"
        :selectedOption="selectedOption"
        @selectOption="selectOption"
        @sortByCategories="sortByCategories"
      />
      <div class="projects-wrapper">
        <div
          class="project"
          v-for="project in filteredProjects"
          :key="project.name"
          :project="project"
          :title="project.name"
        >
          <a :href="project.link" target="_blank" class="project-link">
            <div class="project-info">
              <h3 class="project-name" :style="project.color">
                {{ project.name }}
              </h3>
              <p class="project-description">
                {{ project.description }}
              </p>
              <div class="project-tech-used">
                <img
                  v-for="tech in project.techUsed"
                  :key="tech.name"
                  :src="require('../assets/img/technologies/' + tech.icon)"
                  :alt="tech.name"
                  class="project-tech-icon"
                  width="20"
                  height="20"
                  :title="tech.name"
                />
              </div>
              <img
                :src="
                  require('../assets/img/technologies/' + project.technologyImg)
                "
                :alt="project.category"
                class="project-tag"
              />
            </div>
            <div class="project-image-composition">
              <img
                src="../assets/img/projects/laptop.png"
                alt="laptop"
                class="laptop"
              />
              <div class="project-desktop-img">
                <img
                  :src="
                    require('../assets/img/projects/' + project.projectImage)
                  "
                  :alt="project.name"
                  class="project-img-desktop"
                />
              </div>
              <img
                src="../assets/img/projects/phone.png"
                alt="phone"
                class="phone"
              />
              <div class="project-mobile-img">
                <img
                  :src="
                    require('../assets/img/projects/' +
                      project.projectMobileImage)
                  "
                  :alt="project.name"
                  class="project-img-mobile"
                />
              </div>
            </div>
          </a>
        </div>
      </div>
      <img
        src="../assets/img/thats-all.png"
        alt="that's all folks"
        class="thats-all-img"
      />
    </div>
  </section>
</template>

<script>
import MySelect from "@/components/UI/MySelect";

export default {
  name: "projects",
  components: {
    MySelect,
  },
  data() {
    return {
      selectedOption: "All",
      sortedProjects: [],
      projects: [
        {
          name: "Quiz App",
          description: "Web App created with Vue JS",
          link: "https://yalandr.github.io/quiz-app/",
          projectImage: "quiz-app.png",
          projectMobileImage: "quiz-app-mob.png",
          color: "color:var(--vue-color)",
          category: "vue",
          technologyImg: "vue.png",
          techUsed: [
            {
              name: "vue",
              icon: "vue.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "MovieApp",
          description: "SPA created with Vue JS, REST API, Nuxt JS",
          link: "https://yalandr.github.io/movie-app/",
          projectImage: "movie-app.jpg",
          projectMobileImage: "movie-app-mob.jpg",
          color: "color:var(--vue-color)",
          category: "vue",
          technologyImg: "vue.png",
          techUsed: [
            {
              name: "vue",
              icon: "vue.png",
            },
            {
              name: "nuxt",
              icon: "nuxt.png",
            },
            {
              name: "rest",
              icon: "rest.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "CryptoView",
          description: "SPA created with Vue JS, REST API, Quasar UI",
          link: "https://yalandr.github.io/cryptoview/#/",
          projectImage: "cryptoview.jpg",
          projectMobileImage: "cryptoview-mob.jpg",
          color: "color:var(--vue-color)",
          category: "vue",
          technologyImg: "vue.png",
          techUsed: [
            {
              name: "vue",
              icon: "vue.png",
            },
            {
              name: "quasar",
              icon: "quasar.png",
            },
            {
              name: "rest",
              icon: "rest.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Covid Tracker",
          description: "Web App created with Vue JS, REST API",
          link: "https://yalandr.github.io/vue-covid-tracker/",
          projectImage: "covid-tracker.jpg",
          projectMobileImage: "covid-tracker-mob.jpg",
          color: "color:var(--vue-color)",
          category: "vue",
          technologyImg: "vue.png",
          techUsed: [
            {
              name: "vue",
              icon: "vue.png",
            },
            {
              name: "rest",
              icon: "rest.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Colors Constructor",
          description: "Web App created with Vue JS",
          link: "https://yalandr.github.io/colors-constructor/",
          projectImage: "colors.jpg",
          projectMobileImage: "colors-mob.jpg",
          color: "color:var(--vue-color)",
          category: "vue",
          technologyImg: "vue.png",
          techUsed: [
            {
              name: "vue",
              icon: "vue.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Task List",
          description: "Web App created with Vue JS, LocalStorage",
          link: "https://yalandr.github.io/vue-task-list/",
          projectImage: "task-list.jpg",
          projectMobileImage: "task-list-mob.jpg",
          color: "color:var(--vue-color)",
          category: "vue",
          technologyImg: "vue.png",
          techUsed: [
            {
              name: "vue",
              icon: "vue.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "This Portfolio",
          description: "SPA created with Vue JS",
          link: "https://apollon-comet.github.io/Victor/",
          projectImage: "portfolio.jpg",
          projectMobileImage: "portfolio-mob.jpg",
          color: "color:var(--vue-color)",
          category: "vue",
          technologyImg: "vue.png",
          techUsed: [
            {
              name: "vue",
              icon: "vue.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Exercises App",
          description: "SPA created with React, REST API",
          link: "https://yalandr.github.io/exer-app/",
          projectImage: "exer-app.jpg",
          projectMobileImage: "exer-app-mob.jpg",
          color: "color:var(--react-color)",
          category: "react",
          technologyImg: "react.png",
          techUsed: [
            {
              name: "react",
              icon: "react.png",
            },
            {
              name: "rest",
              icon: "rest.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "House Plan",
          description: "SPA created with React, REST API",
          link: "https://yalandr.github.io/exer-app/",
          projectImage: "house.jpg",
          projectMobileImage: "house-mob.jpg",
          color: "color:var(--react-color)",
          category: "react",
          technologyImg: "react.png",
          techUsed: [
            {
              name: "react",
              icon: "react.png",
            },
            {
              name: "rest",
              icon: "rest.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Rick-and-Morty Pedia",
          description: "SPA created with React, Bootstrap, REST API",
          link: "https://yalandr.github.io/rimpedia/",
          projectImage: "rimpedia.jpg",
          projectMobileImage: "rimpedia-mob.jpg",
          color: "color:var(--react-color)",
          category: "react",
          technologyImg: "react.png",
          techUsed: [
            {
              name: "react",
              icon: "react.png",
            },
            {
              name: "rest",
              icon: "rest.png",
            },
            {
              name: "bootstrap",
              icon: "bootstrap.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Smooth Skin",
          description: "Website based on template made with HTML, CSS, React",
          link: "https://mysmoothskin.jp/",
          projectImage: "skin.jpg",
          projectMobileImage: "skin-mob.jpg",
          color: "color:var(--react-color)",
          category: "react",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "jquery",
              icon: "jquery.png",
            },
          ],
        },
        {
          name: "Instant Weather App",
          description: "Web App created with React, REST API",
          link: "https://yalandr.github.io/react-weather-app/",
          projectImage: "react-weather-app.jpg",
          projectMobileImage: "react-weather-app-mob.jpg",
          color: "color:var(--react-color)",
          category: "react",
          technologyImg: "react.png",
          techUsed: [
            {
              name: "react",
              icon: "react.png",
            },
            {
              name: "rest",
              icon: "rest.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Car Drive",
          description:
            "Multipage Website based on template made with HTML, CSS, React",
          link: "https://mediagalaxy.uk/",
          projectImage: "drive.jpg",
          projectMobileImage: "drive-mob.jpg",
          color: "color:var(--react-color)",
          category: "react",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "jquery",
              icon: "jquery.png",
            },
          ],
        },
        {
          name: "Simple Calculator",
          description: "Web App created with React",
          link: "https://yalandr.github.io/react-simple-calculator/",
          projectImage: "calculator.jpg",
          projectMobileImage: "calculator-mob.jpg",
          color: "color:var(--react-color)",
          category: "react",
          technologyImg: "react.png",
          techUsed: [
            {
              name: "react",
              icon: "react.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "MySnippets",
          description: "Web App created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/snippets/",
          projectImage: "snippets.jpg",
          projectMobileImage: "snippets-mob.jpg",
          color: "color:var(--js-color)",
          category: "js",
          technologyImg: "javascript.png",
          techUsed: [
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Meal Match",
          description: "Web Game created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/meal-match/",
          projectImage: "meal-match.jpg",
          projectMobileImage: "meal-match-mob.jpg",
          color: "color:var(--js-color)",
          category: "js",
          technologyImg: "javascript.png",
          techUsed: [
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "CookApp",
          description:
            "Web App created with HTML, CSS, Javascript, LocalStorage, REST API",
          link: "https://yalandr.github.io/cook-app/",
          projectImage: "cook-app.jpg",
          projectMobileImage: "cook-app-mob.jpg",
          color: "color:var(--js-color)",
          category: "js",
          technologyImg: "javascript.png",
          techUsed: [
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "rest",
              icon: "rest.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Password Generator",
          description: "Web App created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/passw/",
          projectImage: "passw-generator.jpg",
          projectMobileImage: "passw-generator-mob.jpg",
          color: "color:var(--js-color)",
          category: "js",
          technologyImg: "javascript.png",
          techUsed: [
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Quick Currency Converter",
          description: "Web App created with Javascript, REST API",
          link: "https://yalandr.github.io/quick-currency-converter/",
          projectImage: "quick-currency-converter.jpg",
          projectMobileImage: "quick-currency-converter-mob.jpg",
          color: "color:var(--js-color)",
          category: "js",
          technologyImg: "javascript.png",
          techUsed: [
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "rest",
              icon: "rest.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "Panda Tetris",
          description: "Web Game created with Javascript",
          link: "https://yalandr.github.io/JS-Tetris/",
          projectImage: "tetris.jpg",
          projectMobileImage: "tetris-mob.jpg",
          color: "color:var(--js-color)",
          category: "js",
          technologyImg: "javascript.png",
          techUsed: [
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
          ],
        },
        {
          name: "BrokerNear",
          description: "Multipage Website created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/brokernear/",
          projectImage: "brokernear.png",
          projectMobileImage: "brokernear-mob.png",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
          ],
        },
        {
          name: "Cencosud",
          description: "Web Page created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/cencosud/",
          projectImage: "cencosud.jpg",
          projectMobileImage: "cencosud-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
          ],
        },
        {
          name: "Equinor",
          description: "Web Page created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/equinor/",
          projectImage: "equinor.jpg",
          projectMobileImage: "equinor-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
          ],
        },

        {
          name: "Intel AI",
          description: "Web Page created with HTML, CSS, Javascript, Splide JS",
          link: "https://yalandr.github.io/intel-ai/",
          projectImage: "intel-ai.jpg",
          projectMobileImage: "intel-ai-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "splide",
              icon: "splide.svg",
            },
          ],
        },
        {
          name: "Bitcoin Gold",
          description: "Web Page created with HTML, CSS, Javascript, Splide JS",
          link: "https://yalandr.github.io/bitcoin-gold/",
          projectImage: "bitcoin-gold.jpg",
          projectMobileImage: "bitcoin-gold-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "splide",
              icon: "splide.svg",
            },
          ],
        },
        {
          name: "Softpoint",
          description: "Web Page created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/softpoint/",
          projectImage: "softpoint.jpg",
          projectMobileImage: "softpoint-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
          ],
        },
        {
          name: "NFT Holders",
          description: "Web Page created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/nft-holders/",
          projectImage: "nft-holders.png",
          projectMobileImage: "nft-holders-mob.png",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
          ],
        },
        {
          name: "Smartminds",
          description: "Web Page created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/smartminds/",
          projectImage: "smartminds.jpg",
          projectMobileImage: "smartminds-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
          ],
        },
        {
          name: "Sistema Cuantico",
          description: "Web Page created with HTML, CSS, Javascript, JQuery",
          link: "https://yalandr.github.io/sistema-cuantico/",
          projectImage: "sistema-cuantico.jpg",
          projectMobileImage: "sistema-cuantico-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "jquery",
              icon: "jquery.png",
            },
          ],
        },
        {
          name: "Metodo Italiano",
          description: "Web Page created with HTML, CSS, Javascript, JQuery",
          link: "https://yalandr.github.io/metodo-italiano/",
          projectImage: "metodo-italiano.jpg",
          projectMobileImage: "metodo-italiano-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "jquery",
              icon: "jquery.png",
            },
          ],
        },
        {
          name: "Taster",
          description: "Web Page created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/taster/",
          projectImage: "taster.jpg",
          projectMobileImage: "taster-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
          ],
        },
        {
          name: "Techalytic",
          description: "Web Page created with HTML, CSS, Javascript, JQuery",
          link: "https://yalandr.github.io/techalytic/",
          projectImage: "techalytic.jpg",
          projectMobileImage: "techalytic-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
            {
              name: "jquery",
              icon: "jquery.png",
            },
          ],
        },
        {
          name: "Pattern",
          description: "Web Page created with HTML, CSS, Javascript",
          link: "https://yalandr.github.io/pattern/",
          projectImage: "pattern.jpg",
          projectMobileImage: "pattern-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
          ],
        },
        {
          name: "Marketing Agency",
          description:
            "Multipage Website based on template made with HTML, CSS, JQuery",
          link: "https://yalandr.github.io/marketing-agency/",
          projectImage: "marketing-agency.jpg",
          projectMobileImage: "marketing-agency-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "jquery",
              icon: "jquery.png",
            },
          ],
        },
        {
          name: "Media Galaxy",
          description:
            "Multipage Website based on template made with HTML, CSS, JQuery",
          link: "https://mediagalaxy.uk/",
          projectImage: "mediagalaxy.jpg",
          projectMobileImage: "mediagalaxy-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "jquery",
              icon: "jquery.png",
            },
          ],
        },

        {
          name: "Thank You",
          description:
            "Web Page created with HTML, CSS, Javascript, LocalStorage",
          link: "https://yalandr.github.io/thankyou/",
          projectImage: "thankyou.jpg",
          projectMobileImage: "thankyou-mob.jpg",
          color: "color:var(--layout-color)",
          category: "layout",
          technologyImg: "css.png",
          techUsed: [
            {
              name: "html",
              icon: "html-5.png",
            },
            {
              name: "css",
              icon: "css.png",
            },
            {
              name: "javascript",
              icon: "javascript.png",
            },
          ],
        },
      ],
      options: [
        {
          name: "All",
          value: "all",
          background: "background-color:#2196F3",
        },
        {
          name: "Vue JS App",
          value: "vue",
          background: "background-color:var(--vue-color)",
        },
        {
          name: "React App",
          value: "react",
          background: "background-color:var(--react-color)",
        },
        {
          name: "Javascript App",
          value: "js",
          background: "background-color:var(--js-color)",
        },
        {
          name: "Web Page",
          value: "layout",
          background: "background-color:var(--layout-color)",
        },
      ],
    };
  },
  methods: {
    selectOption(option) {
      this.selectedOption = option.name;
      this.sortByCategories(option);
    },
    sortByCategories(option) {
      this.sortedProjects = [];
      let vm = this;
      this.projects.map(function (item) {
        if (item.category === option.value) {
          vm.sortedProjects.push(item);
        }
      });
    },
  },
  computed: {
    filteredProjects() {
      if (this.sortedProjects.length) {
        return this.sortedProjects;
      } else {
        return this.projects;
      }
    },
  },
};
</script>

<style>
.projects-section .section-heading {
  color: var(--projects-color);
  font-size: 40px;
}
.projects-wrapper {
  width: 100%;
  margin-top: 2rem;
  transition: all ease 0.5s;
}
.project {
  width: 100%;
  border-radius: var(--box-border-radius);
  margin: 1rem 0;
  padding: 5rem 0;
}
.project-link {
  display: flex;
  width: 100%;
  height: 100%;
  min-height: 14rem;
  border-radius: var(--box-border-radius);
  border: var(--box-border);
  position: relative;
  padding: 2rem;
  background-color: var(--navbar-bg-color);
  background-image: url(../assets/img/Noise.png);
  transition: 0.2s;
}
.project-link:hover {
  background-color: var(--nav-item-bg);
}
.project-info {
  width: 50%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  position: relative;
}
.project-name {
  font-size: 2.5rem;
  line-height: 130%;
  font-weight: 400;
  margin-bottom: 0.7rem;
  text-shadow: var(--regular-text-shadow);
  position: relative;
  z-index: 2;
}
.project-description {
  background-color: var(--main-bg-color);
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  border: var(--box-border);
  color: var(--default-text-color);
  font-size: 0.9rem;
  line-height: 140%;
  font-weight: 400;
  display: inline-block;
  position: relative;
  z-index: 2;
}
.project-tech-used {
  margin-top: 1rem;
}
.project-tech-icon {
  margin-right: 0.5rem;
}
.project-tag {
  position: absolute;
  height: 100%;
  width: auto;
  top: 0;
  right: 0;
  opacity: 0.2;
}
.project-image-composition {
  width: 50%;
  height: 100%;
  position: relative;
  z-index: 3;
}
.laptop {
  position: absolute;
  top: -5rem;
  display: block;
  max-width: 100%;
  height: auto;
}
.project-desktop-img {
  position: absolute;
  z-index: 1;
  width: 75%;
  aspect-ratio: 8 / 5;
  top: -4.2rem;
  left: 12.5%;
  border-radius: 3px;
  overflow: hidden;
  text-align: center;
}
.project-img-desktop {
  max-height: 100%;
  min-width: 100%;
  height: auto;
  width: 100%;
  max-width: 100%;
}
.project-img-mobile {
  max-width: 100%;
  height: auto;
}
.phone {
  position: absolute;
  z-index: 2;
  width: 28%;
  right: -6%;
  top: 6%;
}
.project-mobile-img {
  position: absolute;
  z-index: 3;
  width: 23%;
  aspect-ratio: 1 / 2.08;
  right: -3.5%;
  top: 0.55rem;
  border-radius: 7px;
  overflow: hidden;
}
.projects-section .btn-wrapper {
  display: flex;
  justify-content: flex-end;
}
.projects-section .btn-wrapper .btn {
  background-color: var(--projects-color);
  margin: 1rem 0;
}
.projects-section .btn-wrapper .btn:hover {
  box-shadow: 0 0 12px var(--projects-color);
}
.thats-all-img {
  display: block;
  width: 100%;
  max-width: 22rem;
  margin: 2rem auto;
}
@media (max-width: 1600px) {
  .laptop {
    top: -4rem;
  }
  .project-desktop-img {
    top: -3.6rem;
  }
}
@media (max-width: 1200px) {
  .project {
    padding: 4rem 0;
  }
  .project-link {
    min-height: 11rem;
  }
  .project-name {
    font-size: 1.8rem;
  }
}
@media (max-width: 992px) {
  .project {
    padding: 3rem 0;
  }
  .project-link {
    min-height: 9rem;
  }
  .project-name {
    font-size: 1.4rem;
    margin-bottom: 0.5rem;
  }
  .project-mobile-img {
    width: 23.4%;
    right: -3.6%;
    border-radius: 3px;
  }
}
@media (max-width: 700px) {
  .project-link {
    padding: 1rem;
    min-height: 7rem;
  }
  .project-description {
    font-size: 0.7rem;
    padding: 0.3rem 1rem;
  }
  .project-tag {
    max-height: 6rem;
  }
  .laptop {
    top: -1.5rem;
  }
  .project-desktop-img {
    top: -1.2rem;
  }
  .project-mobile-img {
    width: 22.5%;
    right: -3.2%;
    border-radius: 2px;
  }
}
@media (max-width: 450px) {
  .project {
    padding: 2rem 0;
  }
  .project-name {
    font-size: 1.2rem;
    margin-bottom: 0.2rem;
  }
  .project-tech-used {
    margin-top: 0.3rem;
  }
  .project-tech-icon {
    margin-right: 0.2rem;
  }
  .laptop {
    max-width: 150%;
    width: 150%;
    left: -2rem;
  }
  .project-desktop-img {
    width: 113%;
    left: -3%;
    border-radius: 2px;
  }
  .phone {
    width: 48%;
    right: -25%;
  }
  .project-mobile-img {
    width: 39%;
    right: -20.5%;
  }
}
@media (max-width: 350px) {
  .section-heading {
    font-size: 2.6rem;
  }
  .project-name {
    margin-bottom: 0.1rem;
  }
  .project-image {
    height: 50%;
  }
  .project-description {
    font-size: 0.6rem;
    padding: 0.2rem 1rem;
  }
}
</style>
