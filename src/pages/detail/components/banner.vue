<template>
  <div>
    <div class="banner" @click="handleGallaryClick()">
      <img class="banner-img" :src="bannerImg"/>
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe63b;</span>  {{this.bannerImgs.length}}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleCloseGallary()"></common-gallary>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'banner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      showGallary: false,
      images: ['http://img1.qunarzz.com/sight/p0/1804/d2/d28d4b47b695a58a3.img.jpg_r_800x800_1ddd2737.jpg', 'http://img1.qunarzz.com/sight/p0/1804/2d/2d82c759bce931b1a3.img.jpg_r_800x800_e55d7a64.jpg']
    }
  },
  components: {
    CommonGallary: CommonGallary,
    FadeAnimation: FadeAnimation
  },
  methods: {
    handleGallaryClick () {
      this.showGallary = true
    },
    handleCloseGallary () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
.banner
  position relative
  overflow hidden
  height 0
  padding-bottom 55%
  .banner-img
    width 100%
  .banner-info
    display flex
    position absolute
    bottom 0
    left 0
    right 0
    line-height .6rem
    color white
    background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
    .banner-title
      flex 1
      font-size .32rem
      padding 0 .2rem
    .banner-number
      height .32rem
      line-height .32rem
      margin-top .14rem
      padding 0 .4rem
      border-radius .2rem
      background rgba(0,0,0,0.8)
      font-size .22rem
    .banner-icon
      font-size: .24rem
</style>
