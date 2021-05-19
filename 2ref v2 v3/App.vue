<template>
  <div>Hello</div>
  <h2>{{num}}</h2>
  <button @click="updateNum">update</button>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "APP",

  //vue2实现方法
  // data(){
  //   return{
  //     num:100
  //   }
  // },
  // methods:{
  //   updateNum(){
  //      this.num++
  //   }
  // },


  //vue3实现方法
  setup(){
    const num =ref(1)
    console.log(num)
    function updateNum(){
      num.value++
    }
    return{
      num,
      updateNum
    }
  }

});
</script>

<style>
</style>
