<template>
  <div class="bg_container"></div>
  <section>
    <ProductDisplay />
  </section>
</template>

<script>
import ProductDisplay from "./components/ProductDisplay.vue";

export default {
  name: "App",
  components: {
    ProductDisplay,
  },
};
</script>

<style>
@import "../src/assets/styles/style.css";
</style>
