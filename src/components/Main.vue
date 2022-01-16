<template>
  <div class="wrapper">
    <div
      class="products-card"
      v-for="object in productsArray"
      v-bind:key="object.id"
    >
      <h3>{{ object.productName }}</h3>
      <img v-bind:src="object.productImage" alt="img" />
      <p>In store: {{ object.productStock }}</p>
      <p>Original price :{{ object.productPrice }}</p>
      <p>Sale price:{{ object.productSalePrice }}</p>
      <button>Add To Cart</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["productsArray"],
  
};
</script>


<style  scoped>
.wrapper {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-column-gap: 15px;
  grid-row-gap: 50px;
  padding: 50px;
}

.products-card {
  width: 250px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  justify-content: space-between;

  background-color: #edede6;
  padding: 15px;
  box-shadow: 0px 2px 2px 3px rgba(84, 84, 84, 0.36);
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

.products-card p:nth-of-type(1) {
  color: rgb(13, 168, 13);
}
</style>