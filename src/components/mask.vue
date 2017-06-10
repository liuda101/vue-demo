<template>
<!--
编辑器设置：
1、使用等宽字体
2、开启空格显示
3、开启tab自动转换空格

编码风格：
0、对齐
1、采用双空格缩进
2、代码块之间加换行
3、属性值使用双引号
-->
<!-- 为动画指定 name，就可以通过几个钩子来设置动画类型；动画开始、结束时会有会触发事件；@事件名即可监听该事件 -->
<transition name="fade" @after-enter="showContent" @after-leave="wrapperDisappeared">
  <!-- v-if: 当表达式的值会 true 时才插入到 dom 中 -->
  <!-- :class 绑定标签属性 -->
  <div class="mask-w" :class="bgType" v-if="wrapperShow">
    <transition name="slide-in-down" @after-leave="hideWrapper">
      <div class="mask" v-if="contentShow">
        <div class="mask-h">
          <!-- 标签内容绑定 -->
          <h2>{{title}}</h2>
          <!-- Icon 子组件使用 -->
          <a @click.prevent="close"><Icon type="close"></Icon></a>
        </div>

        <div class="mask-c">
          <!-- 为组件留个占位符，定制组件具体内容 -->
          <slot></slot>
        </div>

        <div class="mask-f">
          <!-- 监听子组件方法 -->
          <iButton @click="close">{{btnTitle}}</iButton>
        </div>
      </div>
    </transition>
  </div>
</transition>
</template>

<script>
/*
代码风格：
1、不要分号
2、大括号前加空格
3、冒号后加空格
4、方法声明的括号与方法名之间加空格
5、字符串单引号
6、分号后加空格，如 for(let i = 0; i < 10; i++) { ... }
*/
// 引入组件
import iButton from './button'
import Icon from './icon'

export default {
  name: 'mask',
  components: {
    iButton, Icon
  },
  // 组件对外暴露的参数
  props: {
    title: {
      // 参数指定类型
      type: String,
      // 参数指定默认值
      default: ''
    },
    btnTitle: {
      type: String,
      default: '我知道了'
    },
    bgType: {
      type: String,
      default: 'white'
    },
    show: {
      type: Boolean,
      default: false
    }
  },
  // 组件内部数据
  data: function () {
    return {
      wrapperShow: false,
      contentShow: false
    }
  },
  // 组件方法
  methods: {
    showContent: function () {
      this.contentShow = true
    },
    hideWrapper: function () {
      this.wrapperShow = false
    },
    close: function () {
      this.contentShow = false
    },
    wrapperDisappeared: function () {
      this.$emit('disappeared')
    }
  },
  watch: {
    show: function (newVal, oldVal) {
      if (newVal) {
        this.wrapperShow = true
      }
    }
  },
  // 生命周期钩子：当组件挂载到 DOM 结构中之后执行
  mounted: function () {
    // do some network request or other things
  }
}
</script>

<style lang="styl" scoped>
@import "../styl/constant.styl"

.fade-enter, .fade-leave-active
  opacity 0
.fade-enter-active, .fade-leave-active
  transition opacity 0.5s ease-in

.slide-in-down-enter-active, .slide-in-down-leave-active
  transition: opacity 0.2s ease-in-out, transform 0.2s ease-in-out
.slide-in-down-enter, .slide-in-down-leave-active
  opacity 0
  transform translate3d(0, 10%, 0)

.mask-w
  position fixed
  z-index 1000
  top 0
  right 0
  bottom 0
  left 0
  background rgba(255, 255, 255, 0.3)
  &.black
    background rgba(0, 0, 0, 0.618)

.mask
  position absolute
  top 50%
  left 50%
  width 500px
  height 300px
  margin -150px 0 0 -250px
  border-radius 10px
  background #fff

.mask-h
  h2
    margin 0
    line-height 30px
    text-align center
    font-size 16px
    color #4a4a4a
  a
    color #888
    float right
    margin -24px 6px 0 0
    cursor pointer
    &:hover
      color alphaColor

.mask-c
  height 220px
  padding 0 20px
  background #f1f1f1

.mask-f
  padding-top 5px
  text-align center
</style>
