<template>
  <div>
    <h1>Proyecto Vue.js - {{nombrealumno}}</h1>
    

  </div>
</template>
<script >
/*notas independientes */
export default {
  name: "cavecera",
  props: {
    
    nombrealumno:String
  }
};
</script>


<style scoped>
div {
  padding-left: 2%;
}
textarea {
  border-radius: 10px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
