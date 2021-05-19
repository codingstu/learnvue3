<template>
  <h3>m1:{{m1}}</h3>
  <h3>m2:{{m2}}</h3>
  <h3>m3:{{m3}}</h3>
  <h3>m4:{{m4}}</h3>
  <button @click="updateClick">update</button>
</template>

<script>
import { ref,reactive,shallowReactive, shallowRef} from 'vue'
export default {
  name:'App',
  setup(){
    const m1=reactive({
      name:'coderwhy',
      cars:{
        name:'benchi',
        size:20
      }
    })
    const m2=shallowReactive({
      name:'coderwhy',
      cars:{
        name:'sangtana',
        size:20
      }
    })
    const m3=ref({
      name:'coderwhy',
      cars:{
        name:'sam',
        size:20
      }
    })
    const m4=shallowRef({
      name:'coderwhy',
      cars:{
        name:'aodi',
        size:20
      }
    })
    const updateClick=()=>{
      // m1.cars.name ='coderzhang'
      m2.cars.name='coderzhang'
      m3.value.cars.name='coderzhang'
      m4.value.cars.name='coderzhang'
    }
  return{
    m1,
    m2,
    m3,
    m4,
    updateClick
  }
  }
}
</script>

<style>

</style>