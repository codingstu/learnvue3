<template>
  <h2>ref:获取页面中的元素</h2>
  <input type="text" ref="inputRef">
</template>

<script>
import { onMounted, ref } from "vue";
export default {
  name:'App',

  setup(){
    const inputRef =ref(null)
    onMounted(()=>{
      inputRef.value&&inputRef.value.focus()
    })
    return {
      inputRef
    }
  }
}
</script>

<style>

</style>