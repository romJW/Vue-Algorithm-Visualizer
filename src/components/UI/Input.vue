<template>
    <input
          class="input input-bordered input-primary w-full max-w-xs"
          :value = "modelValue" @input = "updateInput"
        />
</template>
<script>
export default {
    props: {
        modelValue:[String, Number]
    },

    methods:{
        updateInput(event){
        this.$emit('update:modelValue', event.target.value)
        }
    }
}
</script>
