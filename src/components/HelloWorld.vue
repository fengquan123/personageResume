<template>
  <div class="hello">
    <ul v-for="(user,index) in sunny" :key="index">
      <li>
        <h2 v-on:click="fun(index)" :style="user.show == true ? 'color:red': '' ">{{user.name}}</h2>
        <h3 v-show="user.show" v-for="(item,index) in user.position" :key="index" >
          <div v-show="item != ''">{{item}}</div>
          <button v-on:click="btn(index)" v-show="item != ''">删除</button>
        </h3>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    sunny:{
      type:Array,
      required:true
    }
  },
  created(){
  },
  methods:{
    fun(e){
      for(var i=0;i<this.$props.sunny.length;i++){
          i!=e ? this.$props.sunny[i].show=false :this.$props.sunny[e].show=!this.$props.sunny[e].show
      }
    },
    btn(e){
      for(var i=0;i<this.$props.sunny.length;i++){
        if(this.$props.sunny[i].show == true ){
          // delete this.$props.sunny[i].position[e]
          this.$props.sunny[i].position.splice(e,e+1);
          console.log(this.$props.sunny[i].position);
        }
      }
    }
   
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
