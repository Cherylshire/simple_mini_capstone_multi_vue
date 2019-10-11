<template>
  <div class="products-show">
    <h1>{{ product.name }}</h1>
    <h4>Price: {{ product.price }}</h4>
    <h4>Description: {{ product.description }}</h4>
    <img v-bind:src="product.image_url" v-bind:alt="product.name">
  </div>
</template>

<style>
</style>

<script>
  var axios = require('axios')

export default {
  data: function() {
    return {
      product: {
        formatted: {
          
        }
      }
    };
  },
  created: function() {
    axios
      .get("/api/products/" + this.$route.params.id) // to access the ":id" wild card in router.js
      .then(response => {
        this.product = response.data;
      });
  },
  methods: {}
};
</script>
