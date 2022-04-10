<template>
  <div class="dialog" v-if="show" @click="hideDialog" @keyup.esc="hideDialog">
    <div @click.stop class="dialog-content">
      <slot></slot>
    </div>
  </div>
</template>
<script>
export default {
  name: 'my-dialog',
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    hideDialog() {
      this.$emit('update:show', false);
    },
  },
};
</script>
<style scoped>
.dialog {
  display: flex;
  position: fixed;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.5);
}

.dialog-content {
  margin: auto;
  padding: 20px;
  background-color: white;
  min-width: 50px;
  min-height: 50px;
  border-radius: 12px;
}
</style>
