<template>
  <div class="wrapper">
    <ul class="prime-nav-block">
      <li
        v-bind:key="index"
        v-for="(item, index) in navbarContent"
        v-on:click="logCategories(item.children)"
      >
        {{ item.title }}
        <ul v-if="item.title == 'Categories ▽' && subCategories.length > 0" class="subcats">
          <li>{{ subCategories[0] }}</li>
          <li>{{ subCategories[1] }}</li>
          <li>{{ subCategories[2] }}</li>
        </ul>
      </li>
    </ul>

    <p class="cart">🛒</p>
  </div>
</template>

<script>
import navbar from "../navbar.json";
export default {
  data() {
    return {
      navbarContent: navbar,
      subCategories: [],
    };
  },
  methods: {
    logCategories(kids) {
      if (this.subCategories.length > 0) {
        this.subCategories = [];
      } else {
        for (let i of kids) {
          console.log(i.title);

          this.subCategories.push(i.title);
        }
      }
    },
  },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 0px;
  background-color: #5bccf6;
  max-height: 99px;
}
.anchor-tags a {
  margin: 25px;
  font-weight: bold;
  color: #030e12;
  text-decoration: none;
}

.wrapper input {
  padding: 2px 4px;
  margin-right: 340px;
  border: none;
  border-radius: 5px;
}
.wrapper p {
  width: 30px;
  height: 30px;
  border: solid 1px #000;
  border-radius: 100%;
  margin-right: 30px;
  font-size: 1.2rem;

  display: flex;
  justify-content: center;
  align-items: center;
}
.prime-nav-block {
  display: flex;
  align-items: center;

}
.prime-nav-block li {
  list-style-type: none;
  margin: 25px;
}
.wrapper .subcats {
  display: block;
  width: 70px;
  background-color: #fcde67;
  padding: 15px;
  position: absolute;
  top: 10;
  
 
}

.wrapper .subcats li {
 
  color: #fff;
  text-align: start;
  font-size: .9rem;
  list-style-type: none;
  margin: 0px;
  margin-top: 10px;
}

.prime-nav-block li{
    position: relative;
}
</style>

