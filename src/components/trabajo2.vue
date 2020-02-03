<template>
  <div><p>Desarollado por "{{nombrealu}}"</p></div>
</template>
<script >
/*notas independientes */
export default {
  name: "pie",
  props: {
    nombrealu: String
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
p{
  text-align: center;
  font-size: 70%
}
</style>
