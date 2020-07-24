<template>
  <div>
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banners="banners"/>
    <recommend-view :recommends="recommends"/>
  </div>
</template>

<script>

  import NavBar from "components/common/navbar/NavBar";
  import { getHomeMultidata } from 'network/home';
  import HomeSwiper from "./HomeSwiper";
  import RecommendView from "./RecommendView";


  export default {
    name: "Home",
    data(){
      return {
        banners: [],
        recommends: []
      }
    },
    components: {
      RecommendView,
      NavBar,
      HomeSwiper,
    },
    created() {
      getHomeMultidata().then(res => {
        this.banners = res.data.banner.list
        this.recommends = res.data.recommend.list
      })
    }
  }
</script>

<style scoped>
  .home-nav {
    background-color: var(--color-text);
    color: #FFFFFF;
  }
</style>
