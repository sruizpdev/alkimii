<template>
  <div id="app">
    <VuePhoneNumber msg="Vue Phone Number" />
  </div>
</template>

<script>
import VuePhoneNumber from "./components/VuePhoneNumber.vue";

export default {
  name: "app",
  components: {
    VuePhoneNumber
  }
};
</script>

<style>
body {
  background-color: rgb(230, 230, 230);
}
</style>
