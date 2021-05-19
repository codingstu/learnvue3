<template>
  <h2>{{color}}</h2>
  <h3>son</h3>
  <GrandSon />
</template>

<script>
import GrandSon from "./GrandSon";
export default {
    name:'Son',
    components:{
        GrandSon
    }
    
}
</script>

<style>

</style>