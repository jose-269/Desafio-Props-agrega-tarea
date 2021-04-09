<template>
  <div id="app">
    <div class="tareas mb-4">
      <h2>Tarea</h2>
      <input type="text" placeholder="Ingrese su tarea" v-model="tarea" />
      <button class="btn btn-success ms-1" @click="ingrearTarea()">
        Agregar tarea
      </button>
    </div>
    <Hijo :arreglo="miArreglo" @escucharHijo="varHijo" />
  </div>
</template>

<script>
import Hijo from "@/components/Hijo.vue";

export default {
  name: "App",
  components: {
    Hijo,
  },
  data() {
    return {
      tarea: "",
      miArreglo: [],
    };
  },
  methods: {
    ingrearTarea() {
      if (this.tarea === "") return;
      this.miArreglo.push({ tarea: this.tarea });
      this.borrarCampo();
    },
    borrarCampo() {
      this.tarea = "";
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.tareas {
  display: flex;
  justify-content: center;
  h2 {
    margin: 0;
    padding-right: 1rem;
  }
}
</style>
