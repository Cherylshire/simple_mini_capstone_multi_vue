<template>
  <div class="product-new">

    <ul>
      <li v-for="error in errors">{{ error }}
      </li>
    </ul>
    <form v-on:submit.prevent="submit()">
      
        <div>
          Name: <input type="text" v-model= "newProductName">
        </div>
        <div>
          Price: <input type="text" v-model= "newProductPrice">
        </div>  
        <div>
          Tax: <input type="text" v-model= "newProductTax">
        </div>
        <div>
          Supplier_name: <input type="text" v-model= "newProductSupplierName">
        </div>
        <div>
          Description: <input type="text" v-model= "newProductDescription">
        </div>
        <div>
          Image Url: <input type="text" v-model= "newProductImageUrl">
        </div>

        <input type="submit" value="Create">

    </form>
  </div>
</template>

<style>
</style>

<script>
var axios = require("axios");
export default {
  data: function() {
    return {
      errors: [],
      newProductName: "",
      newProductPrice: "",
      newProductTax: "",
      newProductSupplierName: "",
      newProductDescription: "",
      newProductImageUrl: ""
    };
  },
  created: function() {},
  methods: {
    submit: function() {
      var clientParams = {
        name: this.newProductName,
        price: this.newProductPrice,
        tax: this.newProductTax,
        supplier_name: this.newProductSupplierName,
        description: this.newProductDescription,
        image_url: this.newProductImageUrl
      };

      axios
       .post("/api/products", clientParams)
       .then(response => {
          this.$router.push("/"); // using the router.js as a library to go to a new page.        
       })
       .catch(error => {
          this.errors = error.response.data.errors;
       });
    }
  }
};
</script>