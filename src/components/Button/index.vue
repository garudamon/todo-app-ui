<template>
  <button
    :class="{
      'primary-button': typeof primary != 'undefined' ? true : false,
      'danger-text': typeof danger != 'undefined' ? true : false,
    }"
    :style="styles"
  >
    <slot />
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: ['primary', 'danger', 'styles'],
};
</script>

<style lang="scss" scoped>
button {
  border: 0px;
  cursor: pointer;
  padding: 10px;
  border-radius: 20px;
  width: 100%;
  font-weight: 300;
  &.primary-button {
    background: #189bd5;
    color: white;
  }
  &.danger-text {
    background: transparent;
    color: #dc001a;
  }
}
</style>
