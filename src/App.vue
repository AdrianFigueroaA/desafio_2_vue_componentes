<template>

  <div id="app" > 
    <input v-model="tarea" type="text" autofocus @keyup.enter="agregar"/>
    <button @click="agregar">Agregar tarea</button>

    <div class="tareaAgregada" >
<Tarea v-for="(tarea, i) in tareas " :tarea="tarea":indice="i":key="i" @eliminar="eliminar"></Tarea>
    </div>
    
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

input{

  height: 35px;
}

button{

  height: 35px;
  margin: 15px;
}

body{

  background: green;
}

h1{

text-align: center;

}
#app {
  text-align: center;
}

.tareaAgregada{


  font-family: 'Times New Roman', Times, serif;
  font-weight: bold;
}


.vaciar{
  border: 2px solid black;
  background: red;
  width: 500px;
  margin: auto;
}
</style>



