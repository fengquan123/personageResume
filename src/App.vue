<template>
  <div id="app">
    <index></index>
    <headers></headers>
    <bodys></bodys>
    <div style="height:100px;border-top:1px solid red"></div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import index from "./views/index/index.vue";
import headers from "./views/header/header";
import bodys from "./views/bodys/bodys"
import QRCode from "qrcodejs2";

export default {
  name: "app",
  components: {
    HelloWorld,
    index,
    headers,
    bodys
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
    
  },
  mounted() {
    // var url="http://iguiyu.com/p?sid=56930";
    // this.qrcode(url);
    // console.log('开发网址-->',process.env.BASE_URL);
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
  box-sizing: border-box;
  /* overflow: hidden; */
  /* overflow:scroll; */
}
#app {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
