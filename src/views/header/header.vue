<template>
  <div class="content">
    <div>RedSpite博客</div>
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
  methods: {
    windowScroll() {
      
      // 滚动条距离页面顶部的距离
      // 以下写法原生兼容
      let scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
      function arr(e) {
        for(var i=1;i<5;i++){
          if(i!=e){
            document.querySelector(".content_top>div:nth-child("+i+")").classList.remove("show")
          }else{
            document.querySelector(".content_top>div:nth-child("+i+")").classList.add("show");
          }
        }
      }
      if (scrollTop < 937) {
        document.querySelector(".content").classList.remove("fixed");
      } else if (scrollTop > 937 && scrollTop < 1686) {
        document.querySelector(".content").classList.add("fixed");
        arr(1);
      } else if (scrollTop > 1686 && scrollTop <2435) {
        arr(2);
      } else {
      }
      
    }
  },
  mounted() {
    window.addEventListener("scroll", this.windowScroll);
  }
};
</script>

<style scoped>
.content {
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
.content > div:nth-child(1) {
  height: 100%;
  line-height: 60px;
  width: 45%;
  text-align: center;
  color: #fff;
}
.content > div:nth-child(1):hover {
  cursor: pointer;
}
.content .content_top {
  width: 55%;
  height: 100%;
  display: flex;
}
.content .content_top > div.show {
  color: yellow;
}
.content .content_top > div {
  height: 100%;
  text-align: center;
  width: 11%;
  line-height: 60px;
  color: #fff;
  font-size: 14px;
}
.content .content_top > div:hover {
  color: yellow;
  cursor: pointer;
}
</style>
