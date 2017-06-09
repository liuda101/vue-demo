<template>
<button class="iui-button" :class="classes" @click="handleClick" :disabled="disable">
  <Icon :type="icon" v-if="icon"></Icon>
  <span>
    <slot></slot>
  </span>
</button>
</template>

<script>
import Icon from '../icon'
export default {
  name: 'button',
  props: {
    type: {
      type: String,
      default: 'primary'
    },
    icon: {
      type: String,
      default: ''
    },
    large: {
      type: Boolean,
      default: false
    },
    disable: {
      type: Boolean,
      default: false
    }
  },
  components: {
    Icon
  },
  computed: {
    classes: function () {
      return `iui-button-${this.type} ` + (this.large ? 'iui-button-large' : '')
    }
  },
  methods: {
    handleClick: function (e) {
      this.$emit('click', e)
    }
  }
}
</script>

<style lang="styl">
@import "../../styl/constant.styl"
.iui-button
  color #fff
  font-size 13px
  text-align center
  line-height 30px
  border none
  outline none
  cursor pointer
  border-radius 20px
  background transparent
  transition all 0.15s ease
  box-sizing border-box
  a
    color #fff
  &:hover
    box-shadow 0 2px 6px rgba(0, 0, 0, 0.3)
  .iui-icon
    position relative
    top 1px
  &:active
    transform translate3d(0, 2px, 0)
  &[disabled]
    background #ebebee
    color #a9a9a9
    border 1px solid transparent
    cursor not-allowed
    color lightBg
    &:hover
      box-shadow none
    &:active
      transform none
.iui-button-primary
  background alphaColor
  padding 0 16px
  border 1px solid alphaColor
  &[disabled]
    background #ebebee
    color #a9a9a9
.iui-button-ghost
  border 1px solid #cfc7c1
  color blackText
  background #fff
  padding 0 16px
  &[disabled]
    background #ebebee
    color #a9a9a9
.iui-button-text
  color #999
  &:hover
    color alphaColor
  &:active
    color darkAlphaColor
.iui-button-large
  width 100%
  line-height 36px
</style>
