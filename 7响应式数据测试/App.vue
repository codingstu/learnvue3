<template>
  <div>Hello</div>
  <!-- <h2>{{user.name}}</h2>
  <h2>性别：{{user.gender}}</h2>
  <h2>年龄：{{user.age}}</h2> -->
  <!-- <button @click="updateClick">update</button> -->
  
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue";

export default defineComponent({
  name: "APP",
  setup(){
    const user:any = {
      name:'coderzh',
      age:18,
      cars:['1','2','4','9']
    }
    user.cars[4]='100'
    console.log(user)
    return{
      user
    }
   
  }
});

</script>

<style>
</style>
