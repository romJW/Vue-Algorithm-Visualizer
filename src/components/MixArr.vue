<template>
    <div>
        <h2 class="mb-6 text-2xl">Перемешайте</h2>
        <Button @click="pack">Размешать</Button>
      </div>
</template>
<script>
import Button from "@/components/UI/Button.vue"
export default {
    components:{
        Button
    },
    methods:{
        pack(){
            this.$emit('pack')
        }
    }
    
}
</script>
<style>
    
</style>