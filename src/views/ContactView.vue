<template>
  <section class="contact-section" id="contact">
    <div class="container">
      <h4 class="section-heading">Please Contact ME!</h4>
      <div class="contact-wrapper">
        <div class="contact-wrapper-column">
          <ContactSet />
        </div>
        <div class="contact-animation-column">
          <ContactAnimation />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ContactAnimation from "@/components/ContactAnimation.vue";
import ContactSet from "@/components/ContactSet.vue";

export default {
  name: "contact",
  components: {
    ContactSet,
    ContactAnimation,
  },
};
</script>

<style>
.contact-section .section-heading {
  color: var(--contact-color);
  font-size: 40px;
}
.contact-wrapper {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.contact-wrapper-column,
.contact-animation-column {
  width: 49%;
}
.contact-animation-column {
  position: relative;
  height: 100%;
  min-height: 32rem;
}
@media (max-width: 991.98px) {
  .contact-wrapper {
    flex-direction: column;
  }
  .contact-wrapper-column,
  .contact-animation-column {
    width: 100%;
  }
}
</style>
