<template>
  <div>Hello</div>
  <h2>{{num.name}}</h2>
  <button @click="updateClick">update</button>
  
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue";

export default defineComponent({
  name: "APP",
  setup(){
    const num = reactive({
      name:'zofia',
      age:18,
      list:['1','2','4']
    })
    const updateClick=()=>{
      num.name='fuze'
    }
     return{
    num,
    updateClick
  }
  },
 

});
</script>

<style>
</style>
