<template>
    <!--div  class="card-group">
      <div class="card">
        <ul class="list-group-item">
            <Articulo deck :key="obj" v-for="obj in object" :titulo="obj.title" :precio="obj.price" :disponibles="obj.available_quantity" :vendidas="obj.sold_quantity" :imagen="obj.thumbnail"></Articulo> 
        </ul!>
        </div>
    </div!-->

  <div class="row"> 
    <Articulo deck :key="obj" v-for="obj in object" :titulo="obj.title" :precio="obj.price" :disponibles="obj.available_quantity" :vendidas="obj.sold_quantity" :imagen="obj.thumbnail"></Articulo> 
  </div>

</template>


<script>
import Articulo from './Articulo.vue'
export default {
name: 'ListaDeArticulos',
props: {
    object: []
  },
  components: {
    Articulo
  },
}
</script>

<style>
    .centralizar{
        display: block;
    margin-left: auto;
    margin-right: auto
    }
</style>