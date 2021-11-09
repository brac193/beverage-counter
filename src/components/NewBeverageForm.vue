<template>
  <div>
    <h3>Lub dodaj napój:</h3>
    <form @submit.prevent="addBeverage">
      <input
        type="text"
        v-model="newBeverage"
        name="newBeverage"
        id="newBeverage"
        placeholder="Nazwa nowego napoju, np. rozpuszczalna z mlekiem"
      />
      <button type="submit">Dodaj nowy napój</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "NewBeverageForm",
  data() {
    return {
      newBeverage: "",
    };
  },
  emits: ["newBeverageEvent"],
  methods: {
    addBeverage() {
      this.$emit("newBeverageEvent", this.newBeverage);
      this.newBeverage = "";
    },
  },
};
</script>