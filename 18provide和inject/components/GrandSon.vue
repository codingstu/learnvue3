<template>
  <h2>{{color}}</h2>
  <h3 :style="{color}">{{color}}</h3>
</template>

<script>
import { inject } from 'vue'
export default {
    name:'GrandSon',
    setup(){
        const color = inject('color')

        return{
            color
        }
}
}

</script>

<style>

</style>