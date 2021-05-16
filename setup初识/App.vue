<template>
  <div>Hello</div>
  <h2>{{counter}}</h2>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "APP",
  setup() {
    const counter = 1;
    return {
      counter,
    };
  },
});
</script>

<style>
</style>
