<template>
  <div id="app">
    <div class="container">
      <sidebar />
      <task-list />
      <task-detail />
    </div>
  </div>
</template>

<script>
import '@/assets/scss/styles.scss';

export default {
  name: 'App',
  components: {
    Sidebar: () => import('@/components/Sidebar'),
    TaskList: () => import('@/components/TaskList'),
    TaskDetail: () => import('@/components/TaskDetail'),
  },
  data: () => ({}),
};
</script>
