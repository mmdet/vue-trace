<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-center">
      <span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}} <span class="iconfont arrow-icon">&#xe615;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
.header
  display:flex
  line-height: .86rem
  background: $bgcolor
  color : #fff
  .header-left
    width: .64rem
    float: left
    .back-icon
      text-align : center
      font-size : .4rem
  .header-right
    min-width: 1.04rem
    padding 0.1rem
    float: right
    font-size: .3rem
    color #fff
    .arrow-icon
      margin-left: -.04rem
      font-size: .20rem
  .header-center
    flex: 1
    background : #ffffff
    border-radius : .1rem
    margin-top : .16rem
    height : .60rem
    line-height : .60rem
    margin-left : .05rem
    margin-right : .2rem
    color : #ccc
    padding-left : .2rem
</style>
