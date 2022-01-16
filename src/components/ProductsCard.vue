<template>
  <div>
    
    <div class="products-card">
        Special product
      <h3>{{ product.productName }}</h3>
      <img v-bind:src="product.productImage" alt="img" />
      <p>In store: {{ product.productStock }}</p>
      <p>Original price :{{ product.productPrice }}</p>
      <p>Sale price:{{ product.productSalePrice }}</p>
      <button>Add To Cart</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["product"],
};
</script>

<style scoped>
.products-card {
  width: 250px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  justify-content: space-between;
  margin-left: 20px;
  margin-bottom: 50px;

  background-color: #fcde67;
  padding: 15px;
  box-shadow: 0px 2px 2px 3px rgba(84,84,84,0.36);
  border-radius: 2px;
}

.products-card img {
  width: 180px;
  height: auto;
  margin: 8px 0px;
}

.products-card > p {
  margin: 5px 0px;
}
.products-card button {
  padding: 4px 8px;
  background-color: #252623;
  color: #fff;
}
.products-card p:nth-of-type(1){
  color:rgb(13, 168, 13);
}
</style>