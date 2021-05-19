<template>
  <h3>子组件</h3>
  <h4>{{msg}}</h4>
  <h3>{{count}}</h3>
</template>

<script>
export default {
    name:'Child',
    props:['msg'],

    beforeCreate(){
      console.log('beforeCreate')
    },
    setup(){
      console.log("setup");
      const msg1=()=>{
        console.log('setup中msg1')
      }
      return{
        msg1
      }
    },
    data(){
      return{
        count:90
      }
    },
    methods:{
      msg2(){
        console.log(data中的msg2)
      }
    },
    mounted(){
      console.log(this)
    }
}

</script>

<style>
</style>