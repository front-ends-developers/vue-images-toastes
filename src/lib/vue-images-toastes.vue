<template>
  <div class="image-view-contain" v-if="showFlag">
    <div class="image-view-mask" @click="hideImage"></div>
    <transition name="fade">
      <div class="image-view-body" @click="hideImage">
        <img :src="imgSrc" alt=""/>
      </div>
  </transition>
  </div>
</template>

<script>
export default {
  name: 'vueImagesToastes',
  props:{
    imgUrl: String,
    imgShowFlag: Boolean
  },
  data () {
    return {
      showFlag: false,
      imgSrc: '',
    }
  },
  methods:{
    hideImage() {
      var that = this
      that.showFlag = false
      that.$emit('hideImage',that.showFlag)
    },
  },
  watch:{
    imgUrl:function(newVal) {
      this.imgSrc = newVal
    },
    imgShowFlag:function(newVal) {
      this.showFlag = newVal
    },
  },
  mounted() {
    var that = this
    that.imgSrc = this.imgUrl
    this.showFlag = that.imgShowFlag
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.image-view-contain {
  position: relative;
  width: 100%;

}

.image-view-body {
    position: fixed;
    z-index: 5000;
    /*display: -webkit-flex;
    display: flex;
    justify-content: center;
    align-self: center;*/
    width: 90%;
    max-width: 300px;
    padding: 1.5rem;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    text-align: center;
    border-radius: 3px;
    overflow: hidden;
}

.image-view-body img {
  /*-webkit-flex: 1;
  -moz-flex: 1;
  -ms-flex: 1;
  -o-flex: 1;
  flex: 1;*/
  width: 100%;
}

.image-view-mask {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0,0,0,.5);
  z-index: 2000;
}
</style>
