<template>
  <div>
    <iButton @click="showMask">Show Mask</iButton>
    <iMask :show="maskShow" title="创建任务" bgType="black" @disappeared="maskDisappeared">
      <!-- <p style="margin: 0; color: #555; font-size: 20px;">新建任务都要干嘛呢？</p> -->
    </iMask>
  </div>
</template>

<script>
import iButton from './components/button'
import iMask from './components/mask'

export default {
  name: 'app',
  components: {
    iButton, iMask
  },
  data: function () {
    return {
      maskShow: false
    }
  },
  methods: {
    showMask: function () {
      this.maskShow = true
    },
    maskDisappeared: function () {
      this.maskShow = false
    }
  }
}
</script>
