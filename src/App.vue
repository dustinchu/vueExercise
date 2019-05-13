<template>

<header class="header" :style="{height:(screenHeight)+'px' , Width:(screenWidth)+'px'}">
  <div class="t1">
<a href="WWW.GOOGLE.com" class="icon"><img src="/static/img/logo.png"></a>
<h1>123333</h1>  
<p></p>
<p> Simple, elegant spark bars </p>
<bars
  :data="[1, 2, 5, 9, 5, 10, 3, 5, 8, 12, 1, 8, 2, 9, 10, 2, 9, 4, 5, 6, 7, 3, 2, 3, 5]"
  :gradient="['#ffbe88', '#ff93df']"
  :barWidth="5"
  :growDuration="1">
  
</bars>

  <b-button class ="login" variant="outline-primary">Primary</b-button>
  
  </div>


</header>

</template>

<script>
  export default {
    data () {
    return {
      screenHeight: document.documentElement.clientHeight, // 螢幕高度
      screenWidth : document.documentElement.clientWidth//螢幕寬度
    }
  },
  watch: {
    'screenWidth': function (val) { // 監聽螢幕寬度變化
      var oIframe = document.getElementById('maindiv')
      oIframe.style.width = (Number(val)) + 'px' // '120'是頁面佈局調整，可去除
    },
    'screenHeight': function (val) { // 監聽螢幕高度變化
      var oIframe = document.getElementById('maindiv')
      // alert(this.$store.getters.screenHeight)
      oIframe.style.height = (Number(val) - 40) + 'px'
    }
  },
  mounted () {
    var _this = this
    window.onresize = function () { // 定義視窗大小變更通知事件
      _this.screenWidth = document.documentElement.clientWidth // 視窗寬度
      _this.screenHeight = document.documentElement.clientHeight // 視窗高度
    }
  },
  }
</script>

<style>
.header{
  background :RGBA(49, 51, 56, 1.00);
 

}

.icon{
  position: fixed;
  top: 1rem;
  right: 1rem;
}

.t1{
 padding: 15vh ;
  font-family: Arial, Helvetica, sans-serif;
  -webkit-font-smoothing:antialiased;
  text-align: center;
  color: aliceblue;
  font-size: 14px;
}

.h1{
  margin: 0;
  font-size: 3rem;
  font-weight: 400;
}

.p{
  margin-top: 20vh
}

.login{
  margin-top: 10vh;
  color: aliceblue;

}



</style>