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
    const proxyUser=new Proxy(user,{
      get(target,prop){
        console.log('get')
        return Reflect.get(target,prop)
      },
      set(target,prop,val){
        console.log('set')
        return Reflect.set(target,prop,val)
      },
      deleteProperty(target,prop){
        console.log('deleteProperty')
        return Reflect.deleteProperty(target,prop)
      }
    })
    console.log(proxyUser.name)
    //通过代理对象更新目标对象的属性操作
    proxyUser.name='zofia'
    console.log(user)
    proxyUser.gender='man'
    console.log(user)
    delete proxyUser.name
    console.log(user)
    proxyUser.cars[1]='90'
    console.log(user)

   
  }
});

</script>

<style>
</style>
