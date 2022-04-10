<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button',
};
</script>

<style scoped>
.button {
  padding: 10px;
  background: none;
  border: 1px solid teal;
  color: teal;
  cursor: pointer;
  transition: 0.3s linear;
}

.button:hover {
  background-color: aquamarine;
  color: black;
}
</style>
