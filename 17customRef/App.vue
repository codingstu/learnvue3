<template>
  <h2>{{ keyword }}</h2>
  <input type="text" v-model="keyword" />
</template>

<script lang="ts">
import { customRef, ref, triggerRef } from "vue";

function useDebouncedRef<T>(value: T, delay = 200) {
  let timeOutId: number;
  return customRef((track, trigger) => {
    return {
      get() {
        track();
        return value
      },
      set(newValue:T) {
        clearTimeout(timeOutId);
        timeOutId=setTimeout(()=>{
          value=newValue;
          trigger()
        },delay)
      },
    };
  });
}
export default {
  name: "App",

  setup() {
    // const keyword=ref('abc')
    const keyword = useDebouncedRef("hello", 500);

    return {
      keyword,
    };
  },
};
</script>

<style>
</style>