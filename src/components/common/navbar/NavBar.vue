<template>
  <div class="nav-bar">
    <div class="left"><slot name="left"></slot></div>
    <div class="center"><slot name="center"></slot></div>
    <div class="right"><slot name="right"></slot></div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.nav-bar{
  display: flex;
  line-height: 44px;
  box-shadow: 0 1px 1px 0 rgba(100, 100, 100, .4);
  flex: 1;
}
.left,.right{
  width: 60px;
}
.center{
  flex: 1;
}
</style>
