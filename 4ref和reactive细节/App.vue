<template>
  <h2>{{msg}}</h2>
  <h2>{{m1}}</h2>
  <h2>{{m2}}</h2>
  <button @click="updateClick">update</button>
  <button @click="updatem1">updatem1</button>
  <button @click="updatem2">updatem2</button>
</template>

<script>
import {reactive, ref} from 'vue'
export default {
  name:'App',
  
  setup(){
    const msg=ref('fuze');
    const m1=reactive({
      name:'hello',
      age:18,
      wife:{
        age:80
      }
    });
    const m2=ref({
      name:'coderzhang',
      age:28,
      wife:{
        name:'codingzh',
        age:50
      }
    });
    const updateClick=()=>{
      msg.value='zofia'
    };
     const updatem1=()=>{
      m1.name='zofia'
    };
    const updatem2=()=>{
      m2.value.wife.age=90
    };
    return{
      msg,
      m1,
      m2,
      updateClick,
      updatem1,
      updatem2
    }
  }
}
</script>

<style>

</style>