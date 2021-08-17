<template>
  <div class="text-field mb-20">
    <label>{{ label }}:</label>
    <input :type="type" v-if="type != 'textarea'" />
    <textarea v-else rows="8" />
  </div>
</template>

<script>
export default {
  name: 'TextField',
  props: {
    label: {
      default: '',
    },
    type: {
      default: 'text',
    },
  },
};
</script>

<style lang="scss" scoped>
.text-field {
  display: flex;
  flex-direction: column;
  label {
    color: var(--gray80);
  }
  input,
  textarea {
    border-radius: 5px;
    border: solid 1px var(--gray80);
    padding: 10px;
    &:hover {
      border-color: var(--blue);
    }
  }
}
</style>
