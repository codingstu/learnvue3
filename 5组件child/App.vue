<template>
  <div>父组件</div>
  
  <h3>msg:{{msg}}</h3>
  <button @click="msg+='==='">update</button>
  <Child :msg='msg'></Child>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

import Child from './components/Child.vue';

export default defineComponent({
  name: "APP",
 components:{
   Child
 },
    setup(){
      const msg=ref("what?")
      return{
        msg
      }
    }
});

</script>

<style>
</style>
