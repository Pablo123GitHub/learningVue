<template>
<router-view :products="theProducts" title="Shop our award-winning product line"></router-view>
</template>

<script>



export default {
  name: 'app',
  data () {
    return {
      theProducts: []
    };
  },
  created: function() {
    $.getJSON('https://hplussport.com/api/products.php?function=products')
      .done(data => {
        this.theProducts = data;
      });
}
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
