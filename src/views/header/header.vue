<template>
  <div class="header_content">
    <div @click="btn_boke" >RedSpite博客</div>
    <div class="content_top">
      <div>关于我</div>
      <div>求职意向</div>
      <div>作品集</div>
      <div>技术掌握</div>
      <div>我的经历</div>
      <div>联系我</div>
    </div>
  </div>
</template>


<script>
export default {
  name: "headers",
  props: {},
  created() {},
  data(){
    return{
      height:window.innerHeight
    }
  },
  methods: {
    windowScroll() {
      
      // 滚动条距离页面顶部的距离
      // 以下写法原生兼容
      let scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
        console.log(scrollTop, '------' , this.height*6);

      function arr(e) {
        for(var i=1;i<document.querySelector(".content_top").getElementsByTagName("div").length+1;i++){
          if(i!=e){
            document.querySelector(".content_top>div:nth-child("+i+")").classList.remove("show")
          }else{
            document.querySelector(".content_top>div:nth-child("+i+")").classList.add("show");
          }
        }
      }
      if (scrollTop < this.height) {
        document.querySelector(".header_content").classList.remove("fixed");
      } else if (scrollTop > this.height ) {
        document.querySelector(".header_content").classList.add("fixed");
        arr(1);
        if (scrollTop > this.height*1.8&& scrollTop < this.height*2.8) {
          arr(2);
        } else if (scrollTop > this.height*2.8&& scrollTop < this.height*3.8) {
          arr(3);
        } else if (scrollTop > this.height*3.8&& scrollTop < this.height*4.8) {
          arr(4);
        } else if (scrollTop > this.height*4.8&& scrollTop < this.height*5.8) {
          arr(5);
        } else if (scrollTop > this.height*5.8) {
          arr(6);
        }
      } 
    },
    btn_boke(){},
    
  },
  mounted() {
    window.addEventListener("scroll", this.windowScroll);
    console.log('----->',document.querySelector(".content_top").getElementsByTagName("div").length);
  }
};
</script>

<style scoped>
.header_content {
  background: #2c3e50;
  height: 60px;
  width: 100%;
  display: flex;
}
.fixed {
  position: fixed;
  top: 0;
  z-index: 999;
}
.header_content > div:nth-child(1) {
  height: 100%;
  line-height: 60px;
  width: 45%;
  text-align: center;
  color: #fff;
}
.header_content > div:nth-child(1):hover {
  cursor: pointer;
}
.header_content .content_top {
  width: 55%;
  height: 100%;
  display: flex;
}
.header_content .content_top > div.show {
  color: yellow;
}
.header_content .content_top > div {
  height: 100%;
  text-align: center;
  width: 11%;
  line-height: 60px;
  color: #fff;
  font-size: 14px;
}
.header_content .content_top > div:hover {
  color: yellow;
  cursor: pointer;
}
</style>
