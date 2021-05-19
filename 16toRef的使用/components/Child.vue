<template>
  <h2>length:{{length}}</h2>
  <h2>age:{{age}}</h2>
</template>

<script>
import { computed,toRef } from 'vue';

function useGetLength(age){
    return computed(()=>{
        return age.value.toString().length
    })
}

export default {
    name:'Child',
    props:{
        age:{
            type:Number,
            required:true
        }
    },
    setup(props){
        const length=useGetLength(toRef(props,'age'))
        return{
            length
        }
    }
}
</script>

<style>

</style>