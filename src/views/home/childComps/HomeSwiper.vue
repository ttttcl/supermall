<template>
  <Swiper>
    <swiper-item v-for="item in banners" :key="item.title">
      <a :href="item.link"
        ><img :src="item.image" alt="" @load="imageLoad"
      /></a>
    </swiper-item>
  </Swiper>
</template>

<script>
import { Swiper, SwiperItem } from "components/common/swiper/index.js";
export default {
  components: {
    Swiper,
    SwiperItem,
  },
  data() {
    return {
      isImageLoad: false,
    };
  },
  props: {
    banners: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  methods: {
    imageLoad() {
      if (!this.isImageLoad) {
        this.$emit("swiperImageLoad");
        this.isImageLoad = true;
      }
    },
  },
};
</script>

<style>
</style>