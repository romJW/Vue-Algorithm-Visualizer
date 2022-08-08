<template>
  <div>
    <h2 class="mb-6 text-2xl">Замедлите</h2>
    <Input :value = "modelValue" @input = "updateInput" type="number" placeholder="0" />
  </div>
</template>
<script>
import Input from '@/components/UI/Input.vue';
export default {
     props:{
     modelValue:[String, Number]
     },
    components:{
        Input
    },
     methods:{
        updateInput(event){
        this.$emit('update:modelValue', event.target.value)
        }
    }
};
</script>
