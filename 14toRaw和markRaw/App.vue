<template>
  <h2>{{state}}</h2>
  <button @click="ToRawClick">update</button>
  <button @click="MarkRaw">update2</button>
</template>

<script>
import { markRaw, reactive, toRaw } from '@vue/reactivity'
export default {
  name:'App',

  setup(){
    const state=reactive({
      name:'hello',
      class:{
        name:'coder',
        num:1
        }
      })


    const ToRawClick=()=>{
      const user=toRaw(state)
      user.name='catalina'
      console.log('user')
    }

    const MarkRaw=()=>{
        state.likes=['hello','world']
        console.log('MarkRaw')
    }
    



    return{
      state,
      ToRawClick,
      MarkRaw
    }



  }



}
</script>

<style>

</style>