<template>
<div class="container" @click="handleCloseGallary()">
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="(item, index) in imgs" :key="index">
        <img class="garrlay-img" :src="item"/>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: Array
  },
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    handleCloseGallary () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow inherit
.container
  display flex
  flex-direction column
  justify-content center
  z-index 99
  position fixed
  left 0
  top 0
  bottom 0
  right 0
  background #000
  .wrapper
    height 0
    width 100%
    padding-bottom 100%
    .garrlay-img
      width 100%
    .swiper-pagination
      color white
      bottom -1rem
</style>
