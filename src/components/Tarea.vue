<template>
  <div  class="vaciar">
    {{tarea}}
    <button @click="vaciar">Eliminar tarea</button>
  </div>
</template>

<script>
export default {
name: "Tarea",
  props: {
    tarea: String,
    indice: Number,
  },
  methods: {
    vaciar() {
      this.$emit("eliminar", this.indice);
    },
  },
};
</script>



