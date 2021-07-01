<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="isActive">
      <slot name="item-icon"></slot>
    </div>
    <div v-else>
      <slot name="item-icon-active"></slot>
    </div>
    <div :style="styleActive">
      <slot name="item-text"></slot>
    </div>
  </div>
</template>
<script>
export default {
  name: "TabBarItem",
  props: {
    path: String,
    activeStyle: {
      type: String,
      default: "red"
    }
  },
  data() {
    return {
      // isActive: true
    };
  },
  computed: {
    isActive() {
      return this.$route.path.indexOf(this.path) == -1;
    },
    styleActive() {
      return this.isActive ? {} : { color: this.activeStyle };
    }
  },
  methods: {
    itemClick() {
      // this.$router.push(this.path);
      // this.$router.replace(this.path);
      this.$router.push(this.path).catch(err => {
        // console.log("输出报错", err);
        console.log(this.path);
      });
    }
  }
};
</script>

<style scoped>
.tab-bar-item {
  height: 49px;
  text-align: center;
}
.tab-bar-item img {
  width: 24px;
  height: 24px;
}
</style>
