<template>
  <div class="theme-switcher">
          <button 
            class="switch-btn light"
            @click="switchToLight"
          ></button>
          <button 
            class="switch-btn dark"
            @click="switchToDark"
          ></button>
        </div>
</template>

<script>
export default {
    name: 'ThemeSwitcher',
    methods: {
        switchToLight() {
            document.documentElement.classList.remove('dark');
            document.documentElement.classList.add('light');
        },
        switchToDark() {
            document.documentElement.classList.remove('light');
            document.documentElement.classList.add('dark');
        }
    }
}
</script>

<style>
.theme-switcher {
  display: flex;
  align-items: center;
  margin: 0 auto;
  width: 5.1rem;
  padding: 0.5rem;
  border-radius: 100px;
  background-color: rgba(150, 150, 150, .4);
  backdrop-filter: blur(6px);
  border: var(--box-border);
  transition: .5s
}
.switch-btn {
    display: block;
    width: 1.8rem;
    height: 1.8rem;
    border-radius: 100px;
    border: var(--box-border);
    cursor: pointer
}
.switch-btn.light {
  background-color: #FFF;
  margin-right: 0.5rem;
}
.switch-btn.dark {
  background-color: #0C0C0C;
}
.switch-btn input {
  display: none;
}
@media (max-width: 1100px) { 
    .theme-switcher {
      width: 4.4rem;
      padding: 0.4rem;
    }
    .switch-btn {
        width: 1.6rem;
        height: 1.6rem;
    }
    .switch-btn.light {
      margin-right: 0.4rem;
    }
}
</style>