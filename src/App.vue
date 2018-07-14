<template>
  <div id="app">
    <vue-images-toastes :imgUrl="imgUrl" :imgShowFlag="imgShowFlag" @hideImage="hideImage"></vue-images-toastes>
  </div>
</template>

<script>
import vueImagesToastes from './lib/vue-images-toastes'

export default {
  name: 'app',
  data () {
    return {
      imgShowFlag: false, // 是否弹框显示,true: 显示；false: 不显示
      imgUrl: '', // 图片 src
    }
  },
  components: {
    vueImagesToastes
  },
  methods: {
    showImage(src) {
    var that = this
    that.imgShowFlag = true;
    that.imgUrl = src;
  },
  hideImage(val) {
    var that = this
    that.imgShowFlag = val
  }
  }
}
</script>

<style lang="scss">
  * {
    margin: 0;
    padding: 0;
  }

</style>
