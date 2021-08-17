<template>
  <div class="mb-20">
    <label>{{ label }}:</label>
    <div class="tags">
      <badge
        v-for="v in items"
        :key="v"
        :small="true"
        :dark="true"
        color="red"
        classes="mr-5"
      >
        {{ v }}
      </badge>
      <input
        type="text"
        placeholder="Add Tags..."
        @keydown.tab.prevent="addTags"
        @keydown.enter.prevent="addTags"
        v-model="tag"
        class="ml-5"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Tags',
  props: {
    label: {
      default: '',
    },
  },
  components: {
    Badge: () => import('@/components/Badge'),
  },
  data: () => ({
    items: [],
    tag: '',
  }),
  methods: {
    addTags() {
      this.items.push(this.tag);
      this.$nextTick(() => {
        this.tag = '';
      });
    },
  },
};
</script>

<style lang="scss" scoped>
label {
  color: var(--gray80);
}
.tags {
  border-radius: 5px;
  border: solid 1px var(--gray80);
  padding: 10px;
  &:hover {
    border-color: var(--blue);
  }
  input {
    border: none;
  }
}
</style>
