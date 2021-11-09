<template>
  <div @click="count++">
    <img src="../assets/hot-drink2.png" />
    <button>Ilość {{ kind }} - {{ count }}</button>
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
};
</script>