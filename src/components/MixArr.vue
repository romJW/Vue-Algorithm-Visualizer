<template>
    <div>
        <h2 class="mb-6 text-2xl">Mix blocks</h2>
        <Button @click="pack">Mix up</Button>
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