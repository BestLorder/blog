<template>
  <div id="container" data-PageSwitch>
    <div class="sections">
      <div class="section active" id="section0">
        <div class="intro">
          <h1 class="title">HelloWorld</h1>
          <p>HelloWorld</p>
        </div>
      </div>
      <div class="section" id="section1">
        <div class="intro">
          <h1 class="title">Example</h1>
          <p>HTML markup example to define 4 sections</p>
          <img src="/static/images/example.png"/>
        </div>
      </div>
      <div class="section" id="section2">
        <div class="intro">
          <h1 class="title">Example</h1>
          <p>The plug-in configuration parameters</p>
          <img src="/static/images/example2.png"/>
        </div>
      </div>
      <div class="section" id="section3">
        <div class="intro">
          <h1 class="title">THE END</h1>
          <p>Everything will be okay in the end. If it's not okay, it's not the end.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
    import jQuery from 'jquery'
  import '../../static/lib/js/pageswitch'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
    created(){
        $("#container").PageSwitch({
            index: 1,    //页面开始的索引，0是第一页。
            easing:"linear",   //动画效果。  ease
            duration:500,      //动画执行时间
            loop:true,         //是否循环切换
            pagination:true,   //是否进行分页
            keybosrd:true,     //是否出发键盘事件
            direction : "vertical",    //滑动方向：vertical（竖版）。horizontal（横板）
            callback:function(){
                // $("h1").addClass("slide");
            }
        });
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  #container,.sections,.section{
    height: 100%;
    position: relative;
  }
  #section0,
  #section1,
  #section2,
  #section3{
    background-color: #000;
    background-size: cover;
    background-position: 50% 50%;
  }
  #section0{
    background-image: url(/static/images/1.jpg);
    color: #fff;
    text-shadow:1px 1px 1px #333;
  }
  #section1{
    color: #fff;
    text-shadow:1px 1px 1px #333;
    background-image: url(/static/images/2.jpg);
  }
  #section2{
    background-image: url(/static/images/3.jpg);
    color: #fff;
    text-shadow:1px 1px 1px #666;
  }
  #section3{
    color: #008283;
    background-image: url(/static/images/4.jpg);
    text-shadow:1px 1px 1px #fff;
  }
  #section0 p{
    color: #F1FF00;
  }
  #section3 p{
    color: #00A3AF;
  }
  .left{
    float: left;
  }
  h1{
    font-size: 6em;
    font-weight: normal;
    transform: translateX(-100%);
  }
  p{
    font-size: 2em;
    margin:0.5em 0 2em 0;
  }
  .intro{
    position: absolute;
    top: 50%;
    width: 100%;
    -webkit-transform: translateY(-50%);
    transform: translateY(-50%);
    text-align: center;
  }
  .pages{
    position:fixed;
    list-style: none;
  }
  .vertical.pages{
    right: 10px;
    top: 50%;
  }
  .horizontal.pages{
    left: 50%;
    bottom: 10px;
  }
  .pages li{
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #fff;
    margin: 10px 5px;
    cursor: pointer;
  }
  .horizontal.pages li{
    display: inline-block;
    vertical-align: middle;
  }
  .pages li.active{
    width: 14px;
    height: 14px;
    border: 2px solid #FFFE00;
    background: none;
    margin-left: 0;
  }
  #section0 .title{
    -webkit-transform: translateX(-100%);
    transform: translateX(-100%);
    -webkit-animation: sectitle0 1s ease-in-out 100ms forwards;
    animation: sectitle0 1s ease-in-out 100ms forwards;
  }
  #section0 p{
    -webkit-transform: translateX(100%);
    transform: translateX(100%);
    -webkit-animation: sec0 1s ease-in-out 100ms forwards;
    animation: sec0 1s ease-in-out 100ms forwards;
  }
  @-webkit-keyframes sectitle0{
    0%{
      -webkit-transform: translateX(-100%);
      transform: translateX(-100%);
    }
    100%{
      -webkit-transform: translateX(0);
      transform: translateX(0);
    }
  }
  @keyframes sectitle0{
    0%{
      -webkit-transform: translateX(-100%);
      transform: translateX(-100%);
    }
    100%{
      -webkit-transform: translateX(0);
      transform: translateX(0);
    }
  }
  @-webkit-keyframes sec0{
    0%{
      -webkit-transform: translateX(100%);
      transform: translateX(100%);
    }
    100%{
      -webkit-transform: translateX(0);
      transform: translateX(0);
    }
  }
  @keyframes sec0{
    0%{
      -webkit-transform: translateX(100%);
      transform: translateX(100%);
    }
    100%{
      -webkit-transform: translateX(0);
      transform: translateX(0);
    }
  }

  .slide{
    transform: translateX(0);
    transition: all ease-in-out 500ms;
  }
</style>
