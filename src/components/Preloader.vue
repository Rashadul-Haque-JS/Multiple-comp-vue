<template>
  <div>
    <p v-if="success">This is loaded</p>
    <div class="wrapper" v-if="loading">
      <div class="loads"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loading: true,
      success: false,
    };
  },
  created() {
    setTimeout(() => (this.loading = false), 2000);
    setTimeout(() => (this.success = true), 2000);
  },
};
</script>

<style scoped>
.loads {
  border: 24px groove rebeccapurple;

  display: table-cell;
  border-radius: 100%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  background: #030e12;
  width: 25px;
  height: 25px;
  margin: 20px 0px;
  margin-left: 130px;
}

p {
  width: 80%;
  margin: 0px 20px;
  text-align: center;
  padding: 8px 0px;
  background-color: #5bccf6;
}
</style>