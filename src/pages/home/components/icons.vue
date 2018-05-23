<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
      <div class="icon" v-for="item of page" :key="item.id">
        <div class="icon-img">
          <img class="icon-img-content" :src="item.imgUrl"/>
        </div>
        <p class="icon-desc">{{item.desc}}</p>
      </div>
    </swiper-slide>
      <div v-show="pages.length>1" class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'icons',
  props: {
    iconList: Array
  },
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
    .icons >>> .swiper-container
     width 100%
     height 0
     padding-bottom 50%
  .icons
    padding-top  .1rem
    background #fff
    .icon
      position relative
      overflow hidden
      float left
      padding-left 5%
      width  20%
      height 0
      padding-bottom 20%
      .icon-img
        position absolute
        left 0
        top 0
        right 0
        bottom 0.2rem
        box-sizing border-box
        padding .1rem
        .icon-img-content
          display block
          margin 0 auto
          height 100%
      .icon-desc
        position absolute
        left 0
        right 0
        bottom 0
        height .40rem
        line-height .40rem
        color $darkTextcolor
        text-align center
        ellipsis()
</style>
