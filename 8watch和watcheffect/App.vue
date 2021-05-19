<template>
  <fieldset>
    <legend>姓名操作</legend>
    姓氏：<input type="text" placeholder="请输入姓氏" v-model="user.firstName"><br>
    名字：<input type="text" placeholder="请输入名字" v-model="user.lastName">
  </fieldset>
  <fieldset>
    <legend>计算属性和监视的演示</legend>
    姓名：<input type="text" placeholder="显示姓名" v-model="fullName"><br>
    姓名：<input type="text" placeholder="显示姓名" v-model="fullName2"><br>
    姓名：<input type="text" placeholder="显示姓名" v-model="fullName3"><br>
  </fieldset>
</template>

<script>
import { reactive,computed,watch,ref, watchEffect } from 'vue'

export default {
  name:'App',

  setup(){
     const user=reactive({
       firstName:'coder',
       lastName:'zhang'
  });
  const fullName=computed(()=>{
    return user.firstName+'_'+user.lastName
  });
  //计算属性
  const fullName2=computed({
    get(){
      return user.firstName+'_'+user.lastName
    },
    set(val){
      const names=val.split('_');
      user.firstName=names[0]
      user.lastName=names[1];
    },
  })
//watch
  const fullName3=ref('')
    // watch(user,({firstName,lastName})=>{
    //   fullName3.value=firstName+'_'+lastName
    // },{immediate:true,deep:true})

  watchEffect(()=>{
    fullName3.value=user.firstName+'_'+user.lastName
  });
  watch([()=>user.firstName,()=>user.lastName,fullName3],()=>{
    console.log('Hello')
  })
    return{
      user,
      fullName,
      fullName2,
      fullName3,
    }
  }
 

}
</script>

<style>

</style>