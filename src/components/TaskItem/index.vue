<template>
  <div
    :class="{
      'task-item p-10 pr-20': true,
      completed: data.completed,
      selected: isSelected == true,
    }"
  >
    <div class="check">
      <span class="fa fas fa-check-circle" v-if="data.completed"></span>
      <span class="far fa-circle" v-else></span>
    </div>
    <div class="info pl-10">
      <div class="title font-weight-bold">{{ data.title }}</div>
      <div class="sub-title pt-3 pb-3">{{ data.category }}</div>
      <div v-if="data.priority" class="mt-5">
        <badge :small="true" color="red" :dark="true">Priority</badge>
      </div>
    </div>
    <div class="time" v-if="!data.completed">{{ data.time }}</div>
  </div>
</template>

<script>
export default {
  name: 'TaskItem',
  props: ['data', 'isSelected'],
  components: {
    Badge: () => import('@/components/Badge'),
  },
};
</script>

<style lang="scss" scoped>
.task-item {
  display: flex;
  border-radius: 10px;
  font-size: 14px;
  .check {
    width: 20px;
    font-size: 20px;
    .fas {
      color: var(--blue);
    }
    .far {
      color: #f2f2f2;
    }
  }
  .info {
    flex: 1;
  }
  .time {
    width: 60px;
  }
  &.completed {
    .title {
      text-decoration: line-through;
      color: #999;
    }
  }
  &:hover {
    background-color: #f8f8f8;
  }
  &.selected {
    border: solid 1px #189bd5;
    background-color: rgba($color: var(--blue), $alpha: 0.05);
    .info {
      .title {
        color: var(--blue);
      }
    }
  }
}
</style>
