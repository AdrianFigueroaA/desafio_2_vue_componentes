<template>

  <div id="app" > 
    <input v-model="tarea" type="text" autofocus @keyup.enter="agregar"/>
    <button @click="agregar">Agregar tarea</button>
    <Tarea
      v-for="(tarea, i) in tareas "
      :tarea="tarea"
      :indice="i"
      :key="i"
      @eliminar="eliminar"
    ></Tarea>
  </div>

</template>


<script>
import Tarea from "./components/Tarea";
export default {
  name: "cosasPorhacer",
  data() {
    return {
      tarea: "",
      tareas: [],
    };
  },
  components: {
    Tarea,
  },
  methods: {
    agregar() {
      this.tareas.push(this.tarea);
      this.tarea = "";
    },
    eliminar(indice) {
      this.tareas.splice(indice, 1);
    },
  },
};
</script>



<style lang="scss">

body{

  background: green;
}

h1{

text-align: center;

}
#app {
  text-align: center;
}
</style>



