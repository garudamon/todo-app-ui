<template>
  <aside>
    <header>
      <avatar />
      <btn primary styles="margin-top: 20px"
        ><i class="fa fas fa-plus"></i> Create a Task</btn
      >
    </header>
    <div class="mt-15">
      <Collapsible title="Shortcut" :items="menu1" />
    </div>
    <div class="mt-15">
      <Collapsible title="Lists" :items="menu2" />
    </div>
    <div class="mt-15">
      <Collapsible title="Tags" :items="menu3" badge />
    </div>
  </aside>
</template>

<script>
export default {
  name: 'Sidebar',
  components: {
    Avatar: () => import('@/components/Avatar'),
    Btn: () => import('@/components/Button'),
    Collapsible: () => import('@/components/CollapsMenu'),
  },
  data: () => ({
    menu1: [
      {
        text: 'Today',
        badge: 10,
      },
      {
        text: 'Next 7 Days',
        badge: 53,
      },
      {
        text: 'All Task',
        badge: 63,
      },
    ],
    menu2: [
      {
        text: 'Work',
        badge: 5,
      },
      {
        text: 'Personal',
        badge: 3,
      },
      {
        text: 'School',
        badge: 0,
      },
      {
        text: 'Freelance Stuff',
      },
    ],
    menu3: [
      {
        text: 'Priority',
        badge: 2,
        color: 'red',
        dark: true,
      },
      {
        text: 'To do in future',
        badge: 0,
        color: 'cyan',
        dark: true,
      },
      {
        text: 'Private',
        badge: 0,
        color: 'purple',
        dark: true,
      },
    ],
  }),
};
</script>

<style lang="scss" scoped>
header {
  padding: 20px;
}
</style>
