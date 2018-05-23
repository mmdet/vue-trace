<template>
    <div class="recommed">
      <div class="recommed-title">猜你喜欢</div>
      <ul>
        <router-link tag="li"
                     class="item border-bottom"
                     v-for="item of recommendList"
                     :key="item.id"
                     :to="'/detail/' + item.id">
          <img :src="item.imgUrl" class="item-img"/>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
          </div>
        </router-link>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'recommed',
  props: {
    recommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .recommed
    background #fff
  .recommed-title
    background #fff
    text-indent .2rem
    line-height .8rem
    margin-top .2rem
  .item
    overflow hidden
    display flex
    height 1.9rem
    .item-img
      width 1.7rem
      height 1.7rem
      padding .1rem
    .item-info
      min-width 0
      flex 1
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
      .item-button
        line-height .44rem
        background #ff9300
        color #ffffff
        margin-top .16rem
        padding 0 .2rem
        border-radius .06rem

</style>
