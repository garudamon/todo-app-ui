<template>
  <div class="detail p-20">
    <div class="header">
      <span class="font-weight-bold">TASK DETAIL</span>

      <div class="mark">
        <span class="far fa-circle"></span>
        Mark as Done
      </div>
    </div>
    <div class="h2 pt-15">
      <span class="font-weight-bold">Prepare for meeting with client</span>
    </div>
    <form class="pt-20">
      <div>
        <text-field label="Due Date" type="datetime-local" />
        <text-field label="List" type="text" />
        <tags label="Tags" />
        <text-field label="Notes" type="textarea" />
      </div>
      <btn danger>Delete Task</btn>
    </form>
  </div>
</template>

<script>
export default {
  name: 'TaskDetail',
  components: {
    TextField: () => import('@/components/TextField'),
    Btn: () => import('@/components/Button'),
    Tags: () => import('@/components/Tags'),
  },
};
</script>

<style lang="scss" scoped>
.detail {
  position: relative;

  .header {
    display: flex;
    justify-content: space-between;
    span {
      &:first-child {
        font-size: 12px;
        color: var(--gray80);
      }
    }
    .mark {
      color: var(--blue);
      cursor: pointer;
    }
  }
  form {
    button {
      position: absolute;
      bottom: 20px;
    }
  }
}
</style>
