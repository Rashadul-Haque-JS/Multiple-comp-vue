<template>
  <div>
    <h1>👀</h1>
    <h1 class="greetings">Welcome!</h1>
    <!-- <div>
      <input type="text" v-model="value">
    <p>{{value}}</p>
    </div> -->
    
    
  </div>
</template>

<script>
export default {
	// data(){
  //   return{
  //     value:'hello'
  //   }
  // }

};
</script>


<style scoped>
div {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
h1 {
  color: white;
  font-size: 1.8rem;
  padding: 20px 0px;
  margin-left: 50px;
  font-family: Arial, Helvetica, sans-serif;
}
.greetings {
  margin-right: 180px;
}
</style>