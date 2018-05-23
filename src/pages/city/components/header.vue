<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
.header
  position relative
  overflow hidden
  height .86rem
  line-height .86rem
  background $bgcolor
  color #fff
  text-align center
  .back-icon
    position absolute
    top 0
    left 0
    text-align : center
    font-size : .4rem
    width: .64rem
    color #fff
</style>
