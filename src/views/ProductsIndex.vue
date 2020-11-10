<template>
<div class="products">
  <h1>All Products</h1>
  <div v-for="product in products">
    <!-- <img 
    v-bin:src="product.url"
    v-bind:alt="product.name"/> -->
    <h2>
      {{ product.name }}
      </h2>
      <p>Description:
      {{ product.description }}
      </p>
      <p>General Use:
      {{ product.general_use }}
      </p>
      <p>Price:
      {{ product.price }}
      </p>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      products: [],
    };
  },
      created: function() {
        axios.get("/api/products")
    .then(response => {
      console.log("products index", response);
      this.products = response.data;
    });
  },
  methods: {},
};
</script>

