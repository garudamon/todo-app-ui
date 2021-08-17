<template>
  <span
    :class="{
      badge: true,
      dark: dark,
      primary: primary,
      small: small,
      classes: true,
    }"
    :style="color != '' ? `background:${color}` : ``"
  >
    <slot />
  </span>
</template>

<script>
export default {
  name: 'Badge',
  props: {
    dark: {
      default: false,
    },
    primary: {
      default: false,
    },
    color: {
      default: '',
    },
    small: {
      default: false,
    },
    classes: {
      default: '',
    },
  },
};
</script>

<style lang="scss" scoped>
.badge {
  padding: 7px 12px;
  border-radius: 15px;
  color: #888;
  background-color: #f2f2f2;
  display: inline-block;
  &.dark {
    color: white;
  }
  &.primary {
    background-color: #189bd5;
  }
  &.small {
    padding: 4px 10px;
    font-size: 12px;
  }
}
</style>
