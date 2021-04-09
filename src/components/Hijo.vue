<template>
  <div>
    <section v-if="arreglo && arreglo.length == 0">
      <p>Aquí irán las tareas</p>
    </section>
    <section>
      <ul class="d-inline-flex flex-column text-start">
        <li class="mb-3" v-for="(el, index) in arreglo" :key="index">
          Tarea N°{{ index + 1 }}: {{ el.tarea }}
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "Hijo",
  props: {
    arreglo: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style scoped>
li {
  vertical-align: middle;
}
</style>
