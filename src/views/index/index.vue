<template>
  <div style="overflow: hidden;">
    <ul class="ulImg">
      <li class="li_show">
        <img src="../../images/timg.jpg" alt="">
      </li>
      <li>
        <img src="../../images/timg1.jpg" alt="">
      </li>
      <li>
        <img src="../../images/timg2.jpg" alt="">
      </li>
      <li>
        <img src="../../images/timg3.jpg" alt="">
      </li>
      <li>
        <img src="../../images/timg4.jpg" alt="">
      </li>
    </ul>
    <div class="divTitle">
      <div>
        <div  class="fadesin1">He l lo, &nbsp;&nbsp;I ' m &nbsp;&nbsp;RedSpite</div>
        <div class="fadesin2">一个拥有像素眼的前端工程师</div>
        <div>
          <div class="show fadesin3">关于我</div>
          <div class="fadesin3">我的作品</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "index",
  props: {},
  data() {
    return {};
  },
  //函数调用
  methods: {
    cha() {
      let All = document.querySelectorAll("ul.ulImg>li");
      var i = 0;
      window.setInterval(function() {
        if (i < All.length) {
          All[i].classList.add("li_show");
          for (var j = 0; j < All.length; j++) {
            if (i != j) {
              All[j].classList.remove("li_show");
            }
          }
          i++;
        } else {
          All[i - 1].classList.remove("li_show");
          i = 0;
          All[i].classList.add("li_show");
        }
      }, 5000);
    }
  },
  //计算属性
  watcher: {},
  //在实例初始化之后，数据观测 (data observer) 和 event/watcher 事件配置之前被调用。
  beforeCreate() {},
  //在实例创建完成后被立即调用。在这一步，实例已完成以下的配置：数据观测 (data observer)，属性和方法的运算，watch/event 事件回调。然而，挂载阶段还没开始，$el 属性目前不可见。
  created() {
    
  },
  //在挂载开始之前被调用：相关的 render 函数首次被调用。
  beforeMount() {},
  //el 被新创建的 vm.$el 替换，并挂载到实例上去之后调用该钩子。如果 root 实例挂载了一个文档内元素，当 mounted 被调用时 vm.$el 也在文档内。
  mounted() {
    this.cha();
    console.log(window.innerWidth);
    console.log(window.innerHeight);
  },
  //数据更新时调用，发生在虚拟 DOM 打补丁之前。这里适合在更新之前访问现有的 DOM，比如手动移除已添加的事件监听器
  beforeUpdate() {},
  //由于数据更改导致的虚拟 DOM 重新渲染和打补丁，在这之后会调用该钩子。
  updated() {},
  //keep-alive 组件激活时调用。该钩子在服务器端渲染期间不被调用。
  activated() {},
  //keep-alive 组件停用时调用。该钩子在服务器端渲染期间不被调用。
  deactivated() {},
  //实例销毁之前调用。在这一步，实例仍然完全可用。该钩子在服务器端渲染期间不被调用。
  beforeDestroy() {},
  //Vue 实例销毁后调用。调用后，Vue 实例指示的所有东西都会解绑定，所有的事件监听器会被移除，所有的子实例也会被销毁。该钩子在服务器端渲染期间不被调用。
  destroyed() {}
};
</script>

<style>
.ulImg {
  position: relative;
  height: 100vh;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  width: 100%;
  background: #fff;
  opacity: 0.4;
}
.ulImg li {
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
  list-style: none;
  position: absolute;
  display: none;
}
.ulImg li img {
  width: 100%;
  height: 100vh;
  position: absolute;
  top: 0;
  left: 0;
  list-style: none;
}
ul.ulImg > li.li_show {
  display: block;
  animation: scaleDraw 7s;
}
@keyframes scaleDraw {
  /*定义关键帧、scaleDrew是需要绑定到选择器的关键帧名称*/
  0% {
    transform: scale(1); /*开始为原始大小*/
    opacity: 1;
  }

  50% {
    transform: scale(1.5);
    opacity: 1;
  }

  100% {
    transform: scale(1);
    opacity: 0.5;
  }
}

.divTitle {
  width: 100%;
  height: 100vh;
  z-index: 999;
  position: absolute;
  top: 0;
  box-sizing: border-box;
  
}
.divTitle > div {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
  width: 100%;
  height: 40%;
}
.divTitle > div > div {
  text-align: center;
  height: 30%;
  position: relative;
  opacity: 1;
}
.fadesin1{
  font-size: 60px;
  transform: translateY(0px);
  animation:fadesin1 0.5s ;
}
@keyframes  fadesin1 {
  0%{
    transform: translateY(100px)
  }
  100%{
    transform: translateY(0px)
  }
}
.fadesin2{
  font-size: 20px;
  animation:fadesin2 1s ;
}
@keyframes  fadesin2 {
  0%{
    transform: translateY(100px);
    opacity: 0;
  }
  50%{
    transform: translateY(100px);
    opacity: 0;
  }
  100%{
    transform: translateY(0px);
    opacity: 1;
  }
}
@keyframes  fadesin3 {
  0%{
    transform: translateY(100px);
    opacity: 0;
  }
  50%{
    transform: translateY(100px);
    opacity: 0;
  }
  100%{
    transform: translateY(0px);
    opacity: 1;
  }
}
.fadesin3{
  animation:fadesin3 1.5s;
}
.divTitle > div > div:nth-child(3) > div {
  display: inline-block;
  width: 150px;height:50px;
  line-height: 50px;
  text-align:center;
  background: #ffffff;
  opacity: 1;
  z-index: 99;
  border-radius: 5px;
  margin-left: 10px;
  border:1px solid #000;
}
.divTitle > div > div:nth-child(3) > div.show{
  border:none;
  background:#2c3e50;
  color:#fff;
}
.divTitle > div > div:nth-child(3) > div:hover{
  color:red;
  cursor:pointer;
} 
</style>
