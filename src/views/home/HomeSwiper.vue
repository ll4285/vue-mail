<template>
  <swiper>
    <swiper-item v-for="item in banners">
      <img :src="item.image">
    </swiper-item>
  </swiper>
</template>

<script>
  import { Swiper,SwiperItem } from "components/common/swiper/index";
  export default {
    name: "HomeSwiper",
    props: {
      banners: {
        type: Array,
        default(){
          return []
        }
      }
    },
    components: {
      Swiper,
      SwiperItem
    }
  }
</script>

<style scoped>

</style>
