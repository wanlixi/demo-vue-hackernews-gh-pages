<template>
  <div id="wrapper">
    <div id="header">
        <a href="#/">默认第一页</a>
        <a href="#!/news/4">第四页</a>
        <a href="#!/news/2">第二页</a>
        <a href="#!/new">新增加页</a>

    </div>
    <!-- main view -->
    <router-view
      class="view"
      keep-alive
      transition
      transition-mode="out-in">
    </router-view>
  </div>
</template>

<script type="text/javascript">
  export default {
    ready () {
      console.log(this.$route.params.page)
    }
  }
</script>
<style lang="stylus">
@import "../variables.styl"

html, body
  font-family Verdana
  font-size 13px
  height 100%

ul
  list-style-type none
  padding 0
  margin 0

#header
  width 100%
  height 50px
  background linear-gradient(left,deeppink,gold)
  a
    display inline-block
    width 24.3%
    height 50px
    text-align center
    color #fff
    cursor pointer
    text-decoration none
    font bolder 20px/50px '微软雅黑'
  a:hover
    background-color #cd85f3
    color #fff
  
#wrapper
  background-color $bg
  position relative
  width 85%
  min-height 80px
  margin 0 auto

#header
  position relative
  
.view
  position absolute
  background-color $bg
  width 100%
  transition opacity .2s ease
  box-sizing border-box
  padding 8px 20px
  &.v-enter, &.v-leave
    opacity 0

@media screen and (max-width: 700px)
  html, body
    margin 0
  #wrapper
    width 100%
</style>
