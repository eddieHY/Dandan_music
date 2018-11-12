<template>
  <swiper :options="swiperOption" class="slider">
    <swiper-slide v-for="(banner, index) in data" :key="index">
     <a class="link" target="_blank" :href="banner.linkUrl">
       <img class="link_img" :src="banner.picUrl">
     </a>
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
</template>

<script>
export default {
  name: 'slider',
  props: ['data'],
  data() {
    return {
      swiperOption: {
        autoplay: true,
        setWrapperSize: true,
        pagination: '.swiper-pagination',
        paginationClickable: true,
        mousewheelControl: true,
        observeParents: true
      }
    }
  },
  computed: {
    swiper() {
      return this.$refs.mySwiper.swiper
    }
  },
  mounted() {
    this.swiper.slideTo(3, 1000, false)
  }
}
</script>

<style lang="stylus" scoped>
.slider
  height 150px
  .link
    display: inline-block;
    height: 100%;
  .link_img
    height 100%;
    width 100%
</style>
