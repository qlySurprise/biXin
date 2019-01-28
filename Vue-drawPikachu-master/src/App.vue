<template>
  <div class="wrap">
    <div id="app">
      <pre id="code" ref="code">{{code}}</pre>
    </div>

    <div v-html="styleCode"></div>

    <div id="whale">
      <div class="main">
            <div class="disc1"></div>
            <div class="disc2"></div>
            <div class="square"></div>
        </div>
    </div>
  </div>
</template>
<script src="https://cdn.bootcss.com/mui/3.7.1/js/mui.min.js"></script>
<script>

export default {
  name: 'App',
  components: {
  },
  data(){
    return {
      code: ``,
      finalCode:`
    *{margin: 0; padding: 0; box-sizing: border-box;}
    *::after{
      box-sizing: border-box;
    }
    *::before{
      box-sizing: border-box;
    }
    #code{
      text-align: center;
      overflow: auto;
      height: 100%;
      padding: 15px;
      background: #e2e2e2;
      color: #c13e3e;
    }
    .wrap{
      display: flex;
      flex-direction: column;
      height: 100vh;
    }
    #app{
      flex:1;
      height: 50%;
    }
    #whale{
      flex:1;
      height: 50%;
    
    }
    
      /*
         小狗子你猜下面什么呀。。
      */
   
    #whale{
      height: 100%;
      border: 1px solid green;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #c3bfc3;
    }
    .disc1{
        width: 100px;
        height: 100px;
        border:1px solid red;
        background-color: red;
        margin:100px 0px 0px 100px;
        border-radius:100%;
        float:left;
    }
    .disc2 {
    width: 100px;
    height: 100px;
    border: 1px solid red;
    background-color: red;
    margin: 50px 2px 0px 0px;
    border-radius: 100%; 
    float: left;
    position: relative;
    right: 50px;
    }
    .square{
        width: 100px;
        height: 100px;
        border:1px solid red;
        background-color: red;
        margin: 100px 0px 0px 0px;
        float: left;
        position: relative;
        right: 152px;
      
    }
    .main{
        transform: rotate(45deg);
        margin-left: 138px;
    }
      `
    }
  },
  created(){
    var n=0;
    var time = setInterval(()=>{
      this.code = this.finalCode.substring(0,n)
      n += 1
      code.scrollTop = 100000
      if(n >= this.finalCode.length){
        window.clearInterval(time);
      }
    },18)
  },
  computed:{
    styleCode(){
      return '<style>' + this.code + '</style>'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
