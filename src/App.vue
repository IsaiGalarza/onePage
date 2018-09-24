<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
@font-face {
    font-family: proximaNova;
    src: url(/static/fonts/Madeleina Sans.ttf);
}

body{
  font-family: proximaNova;
}
</style>
