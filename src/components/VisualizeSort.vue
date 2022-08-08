<template>
  <div>
    <h1 class="sort_header text-blue-600 text-4xl mb-10">Algorithm visualizer</h1>
    <div class="sort_interface flex justify-center gap-36 mb-10">
      <MixArr @pack="packArray" />
      <SpeedSet v-model="value" />
        <Algorithms
        @bubble="bubbleSort"
        @insert="insertionSort"
        @select="selectionSort"
        />
    </div>
    <div class="sort_container w-full fixed border rounded-xl border-blue-600 bg-blue-100 py-5">
      <Bar
        class="bar bg-blue-700"
        v-for="(num, i) in array"
        :key="i"
        :style="{ height: num + 'px' }"
      />
    </div>
  </div>
</template>
<script>
import Button from '@/components/UI/Button.vue';
import Bar from '@/components/UI/Bar.vue';
import MixArr from '@/components/MixArr.vue';
import SpeedSet from '@/components/SpeedSet.vue';
import Algorithms from '@/components/Algorithms';
export default {
  components: {
    Button,
    Bar,
    MixArr,
    SpeedSet,
    Algorithms,
  },
  name: 'App',
  data() {
    return {
      array: [],
      size: 30,
      value: 0,
    };
  },
  methods: {
    packArray() {
      this.array = [];
      for (let i = 0; i < this.size; i++) {
        this.array.push(this.ranodomizeNumber(300, 750));
      }
    },
    ranodomizeNumber(min, max) {
      return Math.floor(Math.random() * (max - min + 1)) + min;
    },
    async bubbleSort() {
      let picked;
      do {
        picked = false;
        for (let i = 0; i < this.array.length; i++) {
          if (this.array[i] > this.array[i + 1]) {
            let prev = this.array[i];
            this.array[i] = this.array[i + 1];
            this.array[i + 1] = prev;
            await this.delay();
            picked = true;
          }
        }
      } while (picked);
    },
    async insertionSort() {
      let picked;
      do {
        picked = false;
        for (let i = 1; i < this.array.length; i++) {
          for (let j = i - 1; j > -1; j--) {
            if (this.array[j + 1] < this.array[j]) {
              [this.array[j + 1], this.array[j]] = [this.array[j], this.array[j + 1]];
              await this.delay();
              picked = true;
            }
          }
        }
      } while (picked);
    },
    async selectionSort() {
      let picked;
      let min;
      do {
        picked = false;
        for (let i = 0; i < this.array.length; i++) {
          min = i;
          for (let j = i + 1; j < this.array.length; j++) {
            if (this.array[j] < this.array[min]) {
              min = j;
              await this.delay();
              picked = true;
            }
          }
          if (min !== i) {
            [this.array[i], this.array[min]] = [this.array[min], this.array[i]];
            await this.delay();
            picked = true;
          }
        }
      } while (picked);
    },
    delay() {
      return new Promise((resolve) => setTimeout(resolve, this.value));
    },
  },
  beforeMount() {
    this.packArray();
  },
};
</script>