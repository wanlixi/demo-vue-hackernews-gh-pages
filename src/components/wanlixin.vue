<template>
  <div class="wan-lixin" v-show="user">
      <h1>{{user.name}}</h1>
      <h3>{{user.loc}}</h3>
      <p>{{user.detail}}</p>
  </div>
</template>

<script>
import store from '../store'

export default {

  name: 'WanLixin',

  data () {
    return {
      user: {}
    }
  },

  route: {
    data ({ to }) {
      // Promise sugar syntax: return an object that contains Promise fields.
      // http://router.vuejs.org/en/pipeline/data.html#promise-sugar
      document.title = 'Profile: ' + to.params.id + ' | Vue.js HN Clone'
      return {
        user: {
          name: 'Vue',
          loc: 'Evan You',
          detail: '作为一名Vue.js的忠实用户，我想有必要写点文章来歌颂这一门美好的语言了，我给它的总体评价是“简单却不失优雅，小巧而不乏大匠”，下面将围绕这句话给大家介绍Vue.js，希望能够激发你对Vue.js的兴趣。Vue.js简介Vue.js的作者为Evan You（尤雨溪），任职于Google Creative Lab，虽然是Vue是一个个人项目，但在发展前景上个人认为绝不输于Google的AngularJs，下面我会将Vue与Angular（Angular 1.0+版本）做一些简单的比较。Vue的主要特点就和它官网（http://cn.vuejs.org/）所介绍的那样：（1） 简洁 （2） 轻量 （3）快速 （4） 数据驱动 （5） 模块友好 （6） 组件化'
        }
      }
    }
  }
}
</script>

<style lang="stylus">
@import "../variables.styl"

.wan-lixin
  text-align center
  p
    text-align left
    text-indent 2em
</style>
