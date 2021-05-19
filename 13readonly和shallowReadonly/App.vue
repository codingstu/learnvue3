<template>
  <h2>{{user}}</h2>
  <h2>{{state}}</h2>
  <button @click="updateClick">update</button>
</template>

<script>
import { reactive, readonly,shallowReadonly } from 'vue'

export default {
  name:'App',
  setup(){
    const user = reactive({
      name:'zofia',
      cars:{
        name:'bow',
        size:50
      }
    })
    //readonly深度只读
    // const state = readonly(user)
    //shallowReadonly浅度只读
    const state = shallowReadonly(user)
    const updateClick=()=>{
      state.cars.name='hello'
    }
    return{
      user,
      state,
      updateClick
    }
  }
}
</script>

<style>

</style>