<template>
  <div id="home">
    <nav-bar class="nav-bar">
      <slot slot="center">首页</slot>
    </nav-bar>
    <home-swiper :banners="banners" />

    <recommend-view :recommends="recommends" />
  </div>
</template>

<script>
import HomeSwiper from "./childComps/HomeSwiper";
import RecommendView from "./childComps/RecommendView";

import NavBar from "components/common/navbar/NavBar";

import { getHomeMultidata, getHomeGoods } from "network/home";

export default {
  name: "Home",
  components: {
    NavBar,
    HomeSwiper,
    RecommendView
  },
  data() {
    return {
      banners: [],
      recommends: []
    };
  },
  created() {
    this.getHomeMultidata();
  },
  methods: {
    getHomeMultidata() {
      getHomeMultidata().then(res => {
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;
      });
    }
  }
};
</script>

<style scoped>
.nav-bar {
  background: pink;
  text-align: center;
}
</style>
