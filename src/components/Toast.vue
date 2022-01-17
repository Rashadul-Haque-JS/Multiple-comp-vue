<template>
  <div>
    <p v-if="!visible" :style="{color:color}">{{ hide }}</p>
  </div>
</template>

<script>
export default {
  props: ["hide"],
  data() {
    return { visible: false, color:'red' }
    
  },
  created() {
    setTimeout(() => {
      this.visible = true;
      console.log(this.visible);
    }, 2500);
    
  },
};
</script>

<style  scoped>
p {
  font-size: 1.2rem;
  font-weight: bolder;
  margin: 10px 20px;
  text-align: center;
  padding: 8px 0px;
  color: #5bccf6;
  border: 1px dotted #030e12;
  border-radius: 10px;
}
</style>

