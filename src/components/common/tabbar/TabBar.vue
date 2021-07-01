<template>
  <div class="tab-bar">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "TabBar",
  data() {
    return {};
  }
};
</script>
<style scoped>
.tab-bar {
  display: flex;
  height: 49px;
  background: #f6f6f6;
  justify-content: space-around;
  padding-top: 2px;
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  box-shadow: 0 -1px 1px rgba(100, 100, 100, 0.2);
}
</style>
