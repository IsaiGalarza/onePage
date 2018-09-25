<template>
  <div class="hero" :style="{ backgroundImage: `url('${media}')` }">
    <div class="hero-inner">
      <h1 class="hero-title">
        {{title}}
      </h1>
      <div class="hero-description">
        {{message}}
      </div>
      <div class="hero-actions mt-4">
          <BaseButton
            v-if="primaryCallToAction"
            v-bind:text="primaryCallToAction.text"
            v-bind:btnOnClick="primaryCallToAction.btnOnClick"
            type="primary"
            extraClass="mr-3"
          />

          <BaseButton
            v-if="secondaryCallToAction"
            v-bind:text="secondaryCallToAction.text"
            v-bind:btnOnClick="secondaryCallToAction.btnOnClick"
            type="secondary"
          />
      </div>
    </div>
  </div>
</template>

<script>
import BaseButton from '@/components/BaseButton';

export default {
  name: 'Hero',
  props: {
    media: {
      type: String,
      require: true,
    },
    title: {
      type: String,
      require: true,
    },
    message: {
      type: String,
      default: '',
    },
    primaryCallToAction: Object,
    secondaryCallToAction: Object,
  },
  components: {
    BaseButton,
  },
};
</script>

<style>
.hero {
  position: absolute;
  top: 0;
  left: 0;
  height: 50vh;
  width: 100vw;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.hero-inner {
  text-align: right;
  color: #fff;
  margin-right: 50px;
  width: 50%;
}

.hero-title {
  font-size: 50px;
  text-transform: uppercase;
}

.hero-description {
  font-size: 20px;
  line-height: 25px;
}
</style>
