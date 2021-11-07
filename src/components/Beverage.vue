<template>
  <button @click="count++">Ilość {{ kind }} - {{ count }}</button>
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