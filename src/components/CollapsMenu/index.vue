<template>
  <div class="collapse">
    <div class="h2 font-weight-bold pl-20 pr-20 mb-15" @click="open = !open">
      <span>{{ title }}</span>

      <i class="fa fas fa-chevron-up" v-if="open"></i>
      <i class="fa fas fa-chevron-down" v-else></i>
    </div>
    <ul v-show="open">
      <li
        :class="{ active: active == v.text, 'pr-15': true }"
        v-for="v in items"
        :key="v.text"
        @click="active = v.text"
      >
        <Badge
          v-if="typeof badge != 'undefined'"
          :dark="v.dark"
          :color="v.color"
          :small="true"
        >
          {{ v.text }}
        </Badge>
        <span v-else>{{ v.text }}</span>

        <Badge
          v-if="v.badge && v.badge > 0"
          :dark="active == v.text"
          :primary="active == v.text"
          >{{ v.badge }}</Badge
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Collapse',
  props: ['title', 'items', 'badge'],
  components: {
    Badge: () => import('@/components/Badge'),
  },
  data: () => ({
    open: true,
    active: '',
  }),
};
</script>

<style lang="scss" scoped>
.collapse {
  .h2 {
    display: flex;
    justify-content: space-between;
    cursor: pointer;
  }
  ul {
    list-style: none;
    margin: 0px;
    padding: 0px;
    li {
      padding-left: 20px;
      position: relative;
      padding-top: 7px;
      padding-bottom: 7px;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: space-between;
      font-size: 14px;
      &::before {
        content: '\f58e';
        font-family: 'Font Awesome 5 Free';
        position: absolute;
        left: 5px;
        opacity: 0;
        color: #888;
        font-weight: 900;
        font-size: 12px;
      }
      &:hover {
        background-color: #f8f8f8;
        &::before {
          opacity: 1;
        }
      }
      &.active {
        color: #189bd5;
      }
    }
  }
}
</style>
