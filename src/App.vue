<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logom.png">
    <!--HelloWorld msg="Ingrese el artículo a buscar"/-->
    <h2>Ingrese el artículo a buscar</h2>
      <form>
        <input type="search" placeholder="Artículo a buscar" aria-label="Search" v-model="value">
        <button type="submit" @click="getProductos">Buscar</button>
      </form>
       <ListaDeArticulos :object= 'info'/>
  </div>

  
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import ListaDeArticulos from './components/ListaDeArticulos.vue'
import axios from 'axios'

export default {
  name: 'App',
    data(){
    return{
      info: [],
      value: ""
    }
  },
  components: {
    ListaDeArticulos
  },
   
  methods:{
    getProductos(e) {
        e.preventDefault();
        axios.get(`https://api.mercadolibre.com/sites/MCO/search?q=${this.value}&limit=10`)
        .then(response => (this.info = response.data.results))
     }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
