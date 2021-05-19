<template>
  <h2>{{ state }}</h2>
  <h3>age:{{age}}</h3>
  <button @click="update">update</button>
  <Child :age="age" />
</template>

<script>
import { reactive, toRef, ref } from "vue";
import  Child  from "./components/Child";
export default {
  name: "App",

  components:{
    Child
  },
  setup() {
    const state = reactive({
      name: "coder",
      age: 1000,
    });
    const age = toRef(state, "age");
    const name = ref(state.name);
    const update = () => {
      state.value = 200;
      // age.value= 50;
    };
    return {
      state,
      update,
      age,
      name
    };
  },
};
</script>

<style>
</style>