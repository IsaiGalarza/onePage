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
        <div class="btn btn-primary mr-3">
          {{primaryCallToAction.text}}
        </div>
        <div class="btn btn-secondary">
          {{secondaryCallToAction.text}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BaseHero',
  // En lugar de obtener la información de data, la obtendremos de los props
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
};
</script>

<style>
.hero {
  position: absolute;
  top: 0;
  left: 0;
  height: 100vh;
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
.btn.btn-primary {
  color: #fff;
  background-color: #FF0079;
  border-color: #FF0079;
}
.btn.btn-secondary {
  color: #FF0079;
  border: 2px solid #fff;
  background-color: #fff;
}
</style>
