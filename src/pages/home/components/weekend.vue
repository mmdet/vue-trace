<template>
    <div class="recommed">
      <div class="recommed-title">周末去哪儿</div>
      <ul class="recommed-content">
        <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
          <div class="item-img-wrapper">
            <img :src="item.imgUrl" class="item-img"/>
          </div>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'homeweekend',
  props: {
    weekendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .recommed-content
    background #fff
  .recommed-title
    text-indent .2rem
    line-height .8rem
    margin-top .2rem
  .item-img-wrapper
    overflow hidden
    height 0
    padding-bottom 37.09%
  .item
    .item-img
      width 100%
    .item-info
      padding .1rem
      margin-right  .1rem
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
        padding-bottom .2rem
</style>
