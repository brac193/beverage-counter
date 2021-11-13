<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <div class="cards">
    <div v-for="(bev, index) in beverages" :key="index">
      <beverage :kind="bev" />
    </div>
  </div>
  <new-beverage-form @newBeverageEvent="onNewBeverage" />
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Beverage from "./components/Beverage.vue";
import NewBeverageForm from "./components/NewBeverageForm.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    Beverage,
    NewBeverageForm,
  },
  data() {
    return {
      beverages: ["Herbata", "Kawa prawdziwa", "Kawa rozpuszczalna"],
    };
  },
  methods: {
    onNewBeverage(value) {
      this.beverages.push(value);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(230px, 1fr));
  grid-gap: 20px;
}
.card {
  display: grid;
  grid-template-rows: max-content 250px 1fr;
}

.card img {
  object-fit: fill;
  width: 100%;
  height: 100%;
}
</style>
