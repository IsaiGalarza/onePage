<template>
  <div
    v-bind:class="normalizedButtonClass"
    v-on:click="btnOnClick()"
  >
    {{text}}
  </div>
</template>

<script>
export default {
  name: 'BaseButton',
  // Computed es utilizado para operacion
  // que requieran cierta logica
  computed: {
    // La funcion normalizedButtonClass
    // genera la clase del boton
    // de acuerdo a lo que reciba en los props
    normalizedButtonClass() {
      return `btn btn-${this.type} ${this.extraClass}`;
    },
  },
  props: {
    text: {
      type: String,
      required: true,
    },
    extraClass: {
      type: String,
      default: '',
    },
    type: {
      type: String,
      default: 'primary',
    },
    btnOnClick: {
      type: Function,
      require: true,
    },
  },
};
</script>

<style>

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
