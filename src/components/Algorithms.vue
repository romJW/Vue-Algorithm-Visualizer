<template>
  <div class="algorithms mb-10">
    <h2 class="mb-6 text-2xl">Choose Algorithm</h2>
    <div class="flex justify-center gap-6">
      <Button @click="bubble">Bubble Sort</Button>
      <Button @click="insert">Insertion Sort</Button>
      <Button @click="select">Selection Sort</Button>
    </div>
  </div>
</template>
<script>
import Button from '@/components/UI/Button.vue';
export default {
  components: {
    Button,
  },
  methods: {
    bubble() {
      this.$emit('bubble');
    },
    insert() {
      this.$emit('insert');
    },
    select() {
      this.$emit('select');
    },
  },
};
</script>

