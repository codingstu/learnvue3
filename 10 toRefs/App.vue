<template>
  <h2>父组件</h2>
  <hr />
  <h4>{{name}}</h4>
  <h4>{{age}}</h4>
   <h4>{{name2}}</h4>
  <h4>{{age2}}</h4>
</template>

<script>
import { reactive, toRef, toRefs } from '@vue/reactivity'

function useFeaturex(){
  const state=reactive({
  name2:'uniapp',
  age2:30
})
return{
  ...toRefs(state)
}
}


export default {
  name: "App",
  setup() {
    const state = reactive({
      name:'codingzhang',
      age:18
    })
    const {name,age}= toRefs(state)
    setInterval(() => {
      name.value ='coder'
    }, 1500);

    const {name2,age2}=useFeaturex();
    return{
      name,
      age,
      name2,
      age2
    }
    
  }
}
</script>

<style>
</style>