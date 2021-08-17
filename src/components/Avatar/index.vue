<template>
  <div class="avatar">
    <img src="https://i.pravatar.cc/100" alt="P" />

    <div class="info">
      <div class="h2 font-weight-bold">Phil Norman</div>
      <div class="sub-title">phi@norman.com</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Avatar',
};
</script>

<style lang="scss" scoped>
.avatar {
  display: flex;
  align-items: center;
  img {
    border-radius: 100%;
    height: 50px;
    width: 50px;
    object-fit: cover;
    object-position: 50% 50%;
  }
  .info {
    padding-left: 10px;
  }
}
</style>
