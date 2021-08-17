<template>
  <div class="content">
    <div class="h1 font-weight-bold header p-20">
      <span>Today</span>

      <span class="fa fas fa-sort-amount-down-alt"></span>
    </div>
    <div class="task-list p-10">
      <task-item
        :data="v"
        v-for="(v, i) in items"
        :key="i"
        :isSelected="i == 0"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'TaskList',
  components: {
    TaskItem: () => import('@/components/TaskItem'),
  },
  data: () => ({
    items: [
      {
        title: 'Prepare for meeting with client',
        category: 'Work',
        priority: true,
        time: '02:00pm',
        completed: false,
      },
      {
        title: 'Collect requirement from Marketing',
        category: 'Work',
        time: '11:00am',
        completed: false,
      },
      {
        title: 'Buy a toy for baby',
        category: 'Personal',
        time: '07:00am',
        completed: false,
      },
      {
        title: 'Coffee',
        category: 'Personal',
        time: '05:00am',
        completed: true,
      },
    ],
  }),
  methods: {},
};
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
}
</style>
