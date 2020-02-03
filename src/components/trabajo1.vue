<template>
  <div id="contenedor">
    <input id="cuadro" v-model="nota" v-on:keyup.enter="sunmit" placeholder="¿Qué qieres recordar?" />

    <div v-for="(mensaje, index) of listaMensajes" v-bind:key="index">
      <div id="marco">
        <button style="float:left" v-on:click="terminar(index)">o</button>
        <div id="caja1">
          {{mensaje.nota}}------{{mensaje.prioridad}}-----{{mensaje.estado}}
          <button
            v-on:click="prioridad(index,1)"
          >baja</button>
          <button v-on:click="prioridad(index,2)">normal</button>
          <button v-on:click="prioridad(index,3)">alta</button>
          <button style="float:right" v-on:click="borrar(index)">x</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "contenido",
  data: function() {
    return {
      nota: "",
      listaMensajes: []
    };
  },
  props: {},
  methods: {
    terminar: function(indice) {
      
      this.listaMensajes[indice].estado = true;
      localStorage.setItem("notas-vue", JSON.stringify(this.listaMensajes));
      //this.ordenar();
      
      
    },
    sunmit: function() {
      
      /*
      this.listaMensajes=[]
      
        localStorage.setItem("notas-vue", JSON.stringify(this.listaMensajes));*/
      if (this.nota != "") {
        this.listaMensajes.push({
          nota: this.nota,
          prioridad: 1,
          estado: false
        });
        localStorage.setItem("notas-vue", JSON.stringify(this.listaMensajes));
      
        this.nota = "";
        
      }
    },
    prioridad: function(indice, prioridadx) {
      this.listaMensajes[indice].prioridad = prioridadx;
      localStorage.setItem("notas-vue", JSON.stringify(this.listaMensajes));
      //this.ordenar();
      /*
      let char1 = [];
      let char2 = [];
      let char3 = [];
      
      if (this.listaMensajes == []&& this.listaMensajes.length<=1) {
        //nada
      }else{
      for (var i =0;i<=(this.listaMensajes.length-1);i++) {
        if (this.listaMensajes[i].prioridad == 1) {
          char1.push(this.listaMensajes[i]);
        }
        if (this.listaMensajes[i].prioridad == 2) {
          char2.push(this.listaMensajes[i]);
        }
        if (this.listaMensajes[i].prioridad == 3) {
          char3.push(this.listaMensajes[i]);
        }
      }
      this.listaMensajes = char1 + char2 + char3;
      localStorage.setItem("notas-vue", JSON.stringify(this.listaMensajes));
      }*/
    },
    borrar: function(indice) {
      this.listaMensajes.splice(indice, 1);
      localStorage.setItem("notas-vue", JSON.stringify(this.listaMensajes));
      //this.ordenar();
    }
  },

  created: function() {
    var datos = JSON.parse(localStorage.getItem("notas-vue"));

    if (datos === null) {
      this.listaMensajes = [];
    } else {
      this.listaMensajes = [];
      this.listaMensajes = datos;
     // this.ordenar();
    }
  }/*,
  ordenar: function() {/*
    let char1 = [];
    let char2 = [];
    let char3 = [];

    if (this.listaMensajes == []&&this.listaMensajes.length<=1) {
     //nada 
    }else{
    for (var objeto of this.listaMensajes) {
      if (objeto.prioridad == 1) {
        char1.push(objeto);
      }
      if (objeto.prioridad == 2) {
        char2.push(objeto);
      }
      if (objeto.prioridad == 3) {
        char3.push(objeto);
      }
    }
    this.listaMensajes = char1 + char2 + char3;
    localStorage.setItem("notas-vue", JSON.stringify(this.listaMensajes));
    }
    alert(this.listaMensajes)
  }*/
};
</script>


<style scoped>
div {
  padding-left: 0%;
}
textarea {
  border-radius: 10px;
}

p {
  color: white;
}
#caja1 {
  box-sizing: border-box;
  width: 100%;
  float: none;
}

#marco {
  box-sizing: content-box;
  width: 90%;
  padding: 1%;
  border: solid 2px;
  border-color: gray;
  box-sizing: 80%;
}
#contenedor {
  padding: 2%;
}
#cuadro {
  width: 90%;
}
</style>
