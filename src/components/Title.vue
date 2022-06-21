<template>
  <h1 class="title">{{ title }}</h1>
</template>

<script>
export default {
  props: {
    title: { type: String },
  },
};
</script>

<style>
.title {
  padding: 1px 15px 1px 15px;
  border: 2px solid white;
  background-color: rgba(16, 26, 42, 1);
  color: white;
  text-align: center;
  width: fit-content;
  margin-left: auto;
  margin-right: auto;
}
</style>