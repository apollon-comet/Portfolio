<template>
  <div class="contact-set">
    <a
      :href="contact.link"
      class="contact-item"
      v-for="contact in contacts"
      :key="contact.name"
      target="_blank"
    >
      <img
        :src="require('../assets/img/icons/' + contact.img)"
        width="20"
        height="20"
        :alt="contact.name"
        loading="lazy"
      />
      {{ contact.text }}
    </a>
  </div>
</template>

<script>
export default {
  name: "ContactSet",
  data() {
    return {
      contacts: [
        {
          name: "location",
          text: "Victor Knight, Poland",
          img: "location.png",
          link: "https://www.google.com/maps/place/Pozna%C5%84,+Poland/@52.4100586,16.9157421,12z/data=!4m6!3m5!1s0x470444d2ece10ab7:0xa4ea31980334bfd1!8m2!3d52.406374!4d16.9251681!16zL20vMDV4bnY?entry=ttu",
        },
        {
          name: "telegram",
          text: "@sunshine",
          img: "telegram.png",
          link: "https://telegram.me/sunshine0213",
        },
        {
          name: "email",
          text: "apollon.comet520@gmail.com",
          img: "gmail.png",
          link: "mailto:apollon.comet520@gmail.com",
        },
        {
          name: "skype",
          text: "Skype",
          img: "skype.png",
          link: "https://join.skype.com/invite/p9VlbPxHE9Vs",
        },
        {
          name: "Slack",
          text: "Slack",
          img: "slack.png",
          link: "https://app.slack.com/client/T05F80QSJNQ/C05F5H8N7S6",
        },
      ],
    };
  },
};
</script>

<style>
.contact-set {
  width: 100%;
}
.contact-item {
  display: flex;
  align-items: center;
  padding: 1.6rem;
  border: 1px solid hsla(0, 0%, 100%, 0.2);
  background-color: var(--main-bg-color);
  backdrop-filter: blur(5px);
  border-radius: var(--box-border-radius);
  border: var(--box-border);
  box-shadow: var(--box-shadow);
  margin-bottom: 0.3rem;
  transition: all 0.2s ease;
}
.contact-item:hover {
  background-color: var(--contact-item-hover-bg);
  border: var(--box-border);
}
.contact-item img {
  margin-right: 1.5rem;
  height: auto;
  filter: drop-shadow(var(--regular-text-shadow));
}
@media (max-width: 600px) {
  .contact-item {
    padding: 1rem;
    font-size: 0.9rem;
  }
}
@media (max-width: 350px) {
  .contact-item {
    padding: 1.5rem 0.8rem;
    font-size: 0.9rem;
  }
  .contact-item img {
    margin-right: 0.5rem;
  }
}
</style>
