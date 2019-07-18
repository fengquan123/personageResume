<template>
  <div id="app">
    <!-- <hello-world v-bind:sunny="sun" v-show="false"></hello-world> -->
    <index></index>
    <headers></headers>
    <about></about>
    <job-wanted></job-wanted>
    <div style="height:100vh;"></div>
    <!-- <div id="qrcode" ref="qrcode"></div> -->
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import index from "./views/index/index.vue";
import headers from "./views/header/header";
import about from "./views/about/about";
import jobWanted from "./views/jobWanted/jobWanted.vue";
import QRCode from "qrcodejs2";

export default {
  name: "app",
  components: {
    HelloWorld,
    index,
    headers,
    about,
    jobWanted
  },
  data() {
    return {
      sun: [
        {
          id: 1,
          name: "luffy",
          position: ["船长", "考古学家", "船医", "剑豪", "航海士", "阻击手"],
          show: false
        },
        {
          id: 2,
          name: "robin",
          position: ["船医", "剑豪", "航海士", "阻击手"],
          show: false
        },
        {
          id: 3,
          name: "chopper",
          position: ["船长", "考古学家", "船医", "剑豪"],
          show: false
        },
        {
          id: 4,
          name: "nami",
          position: ["船长", "考古学家", "船医", "剑豪", "航海士", "阻击手"],
          show: false
        },
        {
          id: 5,
          name: "usopp",
          position: ["船长", "考古学家", "船医", "剑豪", "航海士", "阻击手"],
          show: false
        },
        {
          id: 6,
          name: "sanji",
          position: ["船长", "考古学家", "船医", "剑豪", "航海士", "阻击手"],
          show: false
        }
      ]
    };
  },
  created() {},
  methods: {
    // qrcode() {
    //   let qrcode = new QRCode("qrcode", {
    //     width: 200, // 设置宽度，单位像素
    //     height: 200, // 设置高度，单位像素
    //     text: "https://www.baidu.com" // 设置二维码内容或跳转地址
    //   });
    // }
    // qrcode(url) {
    //   let qrcode = new QRCode("qrcode", {
    //     width: 150, //图像宽度
    //     height: 150, //图像高度
    //     colorDark: "#000000", //前景色
    //     colorLight: "#ffffff", //背景色
    //     typeNumber: 4,
    //     correctLevel: QRCode.CorrectLevel.H //容错级别 容错级别有：（1）QRCode.CorrectLevel.L （2）QRCode.CorrectLevel.M （3）QRCode.CorrectLevel.Q （4）QRCode.CorrectLevel.H
    //   });
    //   qrcode.clear(); //清除二维码
    //   qrcode.makeCode(url); //生成另一个新的二维码
    // },
    
  },
  mounted() {
    // var url="http://iguiyu.com/p?sid=56930";
    // this.qrcode(url);
    console.log('开发网址-->',process.env.BASE_URL);
    this.$axios({
      methods:'get',
      url:process.env.BASE_URL+'/product/details.php?lid=1',
      data:'',
    }).then(res=>{
      console.log('成功->',res.data.details);
    })
  }
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  /* overflow: hidden;
 overflow:scroll; */
}
#app {
  margin: 0;
  padding: 0;
  width: 99vw;
  box-sizing: border-box;
}
</style>
