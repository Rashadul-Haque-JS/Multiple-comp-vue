<template>
  <div class="toggle-button">
    <p>On/Off</p>
    <p @click="toggleRefresh">🔄</p>
    <toggle-one @click.native="showTgOne" />
    <p v-if="showToggleOne">{{ toggle[0] }}</p>

    <toggle-two @click.native="showTgTwo" />
    <p v-if="showToggleTwo">{{ toggle[1] }}</p>

    <toggle-three @click.native="showTgThree" />
    <p v-if="showToggleThree">{{ toggle[2] }}</p>
  </div>
</template>

<script>
import ToggleOne from "./ToggleOne.vue";
import ToggleTwo from "./ToggleTwo.vue";
import ToggleThree from "./ToggleThree.vue";


export default {
  data() {
    return {
      showToggleOne: false,
      showToggleTwo: false,
      showToggleThree: false,
    };
  },
  methods: {
    showTgOne() {
      if (this.showToggleOne == false) {  //Here if statement is only for turning off the toggle by another click. It's a varriation of 'toggleRefresh()' function.
        this.showToggleOne = true;
        this.showToggleTwo = false;
        this.showToggleThree = false;
      } else {                   
        this.showToggleOne = false;
      }
    },
    showTgTwo() {
      if (this.showToggleTwo == false) {
        this.showToggleOne = false;
        this.showToggleTwo = true;
        this.showToggleThree = false;
      } else {
        this.showToggleTwo = false;
      }
    },
    showTgThree() {
      if (this.showToggleThree == false) {
        this.showToggleOne = false;
        this.showToggleTwo = false;
        this.showToggleThree = true;
      } else {
        this.showToggleThree = false;
      }
    },

    // Another method to send all toggle properties in state position
    toggleRefresh() {
      this.showToggleOne = false;
      this.showToggleTwo = false;
      this.showToggleThree = false;
    },
  },
  components: { ToggleOne, ToggleTwo, ToggleThree},
  props: ["toggle"],
};
</script>

<style  scoped>
.toggle-button {
  width: 250px;
  background-color: #030e12;
  text-align: center;
  color: #fff;
  margin-left: 20px;
  margin-top: 40px;
  padding: 15px;
  position: relative;
}

.toggle-button p:nth-of-type(2) {
  position: absolute;
  right: 10px;
  top: 12px;
  cursor: pointer;
}
</style>
