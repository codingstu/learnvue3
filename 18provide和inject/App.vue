<template>
  <h3>父组件</h3>
  <h2>{{color}}</h2>
  <button @click="color='yellow' ">yellow</button>
  <button @click="color='red' ">red</button>
  <button @click="color='green' ">green</button>
  <Son />
</template>

<script>

import { ref ,provide} from "vue";
import Son from "./components/Son";
export default {
  name:'App',
  components:{
    Son
  },
  setup(){
    const color=ref('red');
    provide('color',color);
    return{
      color 
    }
  }
};
</script>

<style>
</style>