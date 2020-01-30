<template>
  <main id="app">
    <Products :APIKey="APIKey" />
  </main>
</template>

<script>
import Products from "./components/Products.vue";

export default {
  name: "app",
  components: {
    Products
  },
  data: function() {
    return {
      APIKey: "gLQTvFN06-RBrMNGtip4p6LJJpA6IKw3"
    };
  }
};
</script>
