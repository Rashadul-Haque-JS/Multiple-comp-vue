<template>
<div>
     <div v-if="!keys">
      <div class="loads"></div>
    </div>
  <div class="person-card" v-if="keys">
    <div class="person" v-for="(object, i) in keys.results" :key="i">
      <h2>{{ keys.results[i].name.first }} {{ keys.results[i].name.last }}</h2>
      <img :src="keys.results[i].picture.large" alt="picture of person" />
      <p>Age: {{ keys.results[i].dob.age }}</p>
      <p>Gender: {{ keys.results[i].gender }}</p>
      <p>Title: {{ keys.results[i].name.title }}</p>
      <p>Country: {{ keys.results[i].location.country }}</p>
      <p>State: {{ keys.results[i].location.state }}</p>
      <p>City: {{ keys.results[i].location.city }}</p>
      <p>{{ keys.results[i].email }}</p>
      <p>Phone: {{ keys.results[i].cell }}</p>
    </div>
  </div>
</div>
</template>

<script>
export default {
  props: ["keys"],
};
</script>

<style scoped>
.person-card {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  margin: 50px 0px;
  padding: 30px;
  min-height: 1466px;
}
.person {
  width: 250px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  justify-content: space-between;
  margin-left: 60px;
  margin-bottom: 50px;

  background-color: #812f33;
  padding: 15px;
  box-shadow: 0px 2px 2px 3px rgba(84, 84, 84, 0.36);
  border-radius: 2px;
}

.person img {
  width: 180px;
  height: auto;
  margin: 8px 0px;
}

.loads {
  border: 24px groove rebeccapurple;

  display: table-cell;
  border-radius: 100%;
  animation: spin 1s linear infinite;
  position: absolute;
  top:20px;
  left: 50%;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

</style>