<template>
  <div class="container">
    <div class="hero-container">
      <Hero
        v-bind:title="title"
        v-bind:message="message"
        v-bind:primaryCallToAction="primaryButton"
        v-bind:secondaryCallToAction="secondaryButton"
        v-bind:media="media"
      />
    </div>
  </div>
</template>

<script>
import Hero from '@/components/BaseHero';

export default {
  name: 'Home',
  components: {
    Hero,
  },
  data() {
    return {
      title: 'Perros en la playa',
      message: `Son muchos los perros que al igual que sus amos,
                disfrutan de un buen dia en la playa. En esta página encontrarás
                tips para cuidarlos correctamente.`,
      media: '/static/images/bg_hero.png',
      primaryButton: {
        text: 'Mejores playas para perros',
        btnOnClick: () => {
          console.log('Clicked primary button'); // eslint-disable-line no-console
        },
      },
      secondaryButton: {
        text: 'Contáctanos',
        btnOnClick: () => {
          console.log('Clicked secondary button'); // eslint-disable-line no-console
        },
      },
    };
  },
};
</script>
