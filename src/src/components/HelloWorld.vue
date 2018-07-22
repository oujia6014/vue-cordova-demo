<template>
  <div class="hello">
    <h1 @click="getcode">{{ msg }}</h1>
    <h5>{{reqMessage}}</h5>
    <button @click="getcamera">调用摄像头</button>
    <button @click="getcode">调用二维码扫描</button>
    <button @click="getnetword">获取网络状态</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function () {
    return {
      msg: 'cordova未加载',
      reqMessage: ''
    }
  },
  methods: {
    getcode () {
      this.msg = '调用barcodeScanner'
      window.cordova.plugins.barcodeScanner.scan((success) => {
        this.reqMessage = success.text
      }, (error) => {
        this.reqMessage = error.text
      })
    },
    getcamera () {
      this.msg = '调用camera'
      navigator.camera.getPicture((imageURI) => {
        this.reqMessage = '图片路径:' + imageURI
      }, (message) => {
        this.reqMessage = '失败:' + message
      }, {
        quality: 50,
        destinationType: navigator.camera.DestinationType.FILE_URI
      })
    },
    getnetword () {
      this.msg = '调用获取网络'
      this.reqMessage = navigator.connection.type
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
