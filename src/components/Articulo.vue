<template>
  <div class="card" style="width: 18rem;">
  <img class="card-img-top" :src="imagen" alt="Card image cap">
  <div class="card-body">
      <h5 class="card-title">{{title}}</h5>
      <p class="card-text">Por solo: ${{precio}}</p>
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">Disponibles: {{disponibles}}</li>
    <li class="list-group-item">Vendidas: {{vendidas}}</li>
  </ul>
  <div class="card-body">
    <!--button type="submit" @click="getDetalle" class="btn btn-primary">detalle</button!-->
    <a href="./" class="btn btn-primary">Comprar</a>
  </div>
</div>
</template>
<script>
export default {
  name: "Articulo",
  props: {
    titulo: String,
    precio: Number,
    disponibles: Number,
    vendidas: Number,
    imagen: String
  }
};

</script>

<style>

    .centralizar{
        display: block;
    margin-left: auto;
    margin-right: auto
    }
</style>