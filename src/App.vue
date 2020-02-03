<template>
  <div id="app">
    <cabecera nombrealumno="Jesus Salazar Rivera"></cabecera>
    <contenido>
       
    </contenido>
    <pie nombrealu="Jesus Salazar Rivera"></pie>
  </div>
</template>

<script>
import contenido from "./components/trabajo1.vue";
import pie from "./components/trabajo2.vue";
import cabecera from "./components/trabajo3"
export default {
  name: "app",
  
  data: function() {
    return {
  };
  },
  components: {
    contenido,
    pie,
    cabecera
  },
  props: {
  },
  methods: {}
};

</script>

<style>
body {
  background-color: black;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: aliceblue;
  margin-top: 60px;
}
</style>
