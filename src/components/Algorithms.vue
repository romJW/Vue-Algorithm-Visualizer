<template>
  <div class="algorithms mb-10">
    <h2 class="mb-6 text-2xl">Выберите алгоритм</h2>
    <div class="flex justify-center gap-6">
      <Button @click="bubble">Пузырьковая сортировка</Button>
      <Button @click="insert">Сортировка вставками</Button>
      <Button @click="select">Сортировка выбором</Button>
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

