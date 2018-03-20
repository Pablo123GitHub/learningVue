<template>
  <div>
    <h2><strong>{{product[0].name}}</strong></h2>

    <router-link to="/products">Back to all products</router-link>
    <img :src="product[0].image">
    <p>{{product[0].description}}</p>
    <strong>{{product[0].price}}</strong>
    <div>
      <button>Add to Cart</button>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'product',
    data() {
      return {
        product: {}
      }
    },
    created() {
      let id = this.$route.params.id;
      $.getJSON(`https://hplussport.com/api/products/id/${id}`)
        .done(data => {this.product = data;})
    }
  };
</script>

<style scoped>
  img {
    width: 700px;
    height: 700px;
  }
</style>

