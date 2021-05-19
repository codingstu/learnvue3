<template>
  <button @click="modalOpen=true">打开对话框</button>

     <Teleport to="body">
         <div v-if="modalOpen">
        <div>
            this is modal
        </div>
        <button @click="modalOpen=false">关闭对话框</button>
    </div>
     </Teleport>
    

</template>

<script>
import { ref } from "vue";
export default {
    name:'modalbutton',
    
    setup(){
        const modalOpen=ref(false)
        return{
            modalOpen
        }
    }
}
</script>

<style>

</style>