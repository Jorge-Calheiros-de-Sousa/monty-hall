<template>
  <div id="app">
    <MontyHall />
  </div>
</template>

<script>
import MontyHall from "./main/MontyHall.vue";
export default {
  components: { MontyHall },
};
</script>

<style>
body {
  font-family: "Courier New", Courier, monospace;
  background: rgb(71, 135, 118);
  background: linear-gradient(
    90deg,
    rgba(71, 135, 118, 1) 30%,
    rgba(16, 26, 42, 1) 100%
  );
}
</style>
