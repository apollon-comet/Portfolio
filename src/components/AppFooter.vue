<template>
  <footer class="footer">
    <div class="container">
      <p class="footer-text">@ Victor 2019-{{ currentYear }}</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "AppFooter",
  data() {
    return {
      currentYear: new Date().getFullYear(),
    };
  },
};
</script>

<style>
.footer {
  min-height: 10vh;
}
.footer-text {
  font-size: 0.9rem;
  font-weight: 200;
  color: var(--regular-text-color);
  text-align: center;
}
</style>
