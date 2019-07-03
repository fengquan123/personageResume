<template>
  <div id="app">
    <!-- <hello-world v-bind:sunny="sun" v-show="false"></hello-world> -->
    <index></index>
    <headers></headers>
    <about></about>
    <job-wanted></job-wanted>
    <div style="height:100vh;"></div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import index from './views/index/index.vue'
import headers from './views/header/header'
import about from './views/about/about'
import jobWanted from './views/jobWanted/jobWanted.vue'
export default {
  name: 'app',
  components: {
    HelloWorld,
    index,
    headers,
    about,
    jobWanted
  },
  data(){
    return {
      sun:[
        {id:1,name:'luffy',position:['船长','考古学家','船医','剑豪','航海士','阻击手'],show:false},
        {id:2,name:'robin',position:['船医','剑豪','航海士','阻击手'],show:false},
        {id:3,name:'chopper',position:['船长','考古学家','船医','剑豪',],show:false},
        {id:4,name:'nami',position:['船长','考古学家','船医','剑豪','航海士','阻击手'],show:false},
        {id:5,name:'usopp',position:['船长','考古学家','船医','剑豪','航海士','阻击手'],show:false},
        {id:6,name:'sanji',position:['船长','考古学家','船医','剑豪','航海士','阻击手'],show:false}
      ]
    }
  },
  created(){
    
  }
}
</script>

<style>
body{
 margin:0;
 padding:0;
 /* overflow: hidden;
 overflow:scroll; */
}
#app{
  margin:0;
  padding:0;
  width:99vw;
  box-sizing: border-box;

}
</style>
