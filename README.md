# vue-images-toastes


> A Vue.js vue-images-toastes Plugin


## Install
```shell
npm install vue-images-toastes -S
```

## how to use
```
// main.js
import vueImagesToastes from 'vue-images-toastes'

Vue.use(vueImagesToastes)

// 使用页面
<img :src="src" alt="img" @click="showImage(src)"/>
<vue-images-toastes :imgUrl="imgUrl" :imgShowFlag="imgShowFlag" @hideImage="hideImage"></vue-images-toastes>

data() {
  return {
    // 可传参数
    imgShowFlag: false, // 是否弹框显示,true: 显示；false: 不显示
    imgUrl: '', // 图片 src
  }
}

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
},
```

