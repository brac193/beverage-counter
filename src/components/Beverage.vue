<template>
  <div class="card">
    <h3>{{ kind }}</h3>
    <img src="../assets/hot-drink2.png" />
    <p class="quantity">{{ count }}</p>
    <div class="sign-container">
      <span @click="plusOneDrink()" class="sign">&#43;</span>
      <span @click="minusOneDrinkOrZero()" class="sign">&#8722;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Beverage",
  props: {
    kind: String,
  },
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    plusOneDrink() {
      return this.count++;
    },
    minusOneDrinkOrZero() {
      if (this.count == 0) {
        return this.count;
      } else {
        return this.count--;
      }
    },
  },
};
</script>
<style>
.sign-container {
  width: 100%;
  height: 50px;
  padding: 0;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}
.sign {
  max-width: 50%;
  height: fit-content;
  font-size: 50px;
}
.quantity {
  font-size: 30px;
}
</style>