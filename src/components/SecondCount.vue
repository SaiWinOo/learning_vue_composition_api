<template>
  <div class="flex justify-center flex-col items-center">
    <h4 class="font-bold text-3xl text-green-500">{{ message }}</h4>
    <h4 class="font-bold text-3xl text-green-500"> </h4>
    <div>
      {{ count }}
    </div>
    <div>
      <button @click="subtract" class="bg-green-400 py-2 px-5">-</button>
      <button @click="add" class="bg-green-400 py-2 px-5">+</button>
    </div>
  </div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
  props: {
    message: String
  },
  setup() {
    const count = ref(0);
    const add = () => {
      count.value += 1;
    }
    const subtract = () => {
      count.value -= 1;
    };
    return { count, add, subtract }
  },
  methods: {

  },
  mounted() {
    console.log('mounted')
  }
}
</script>

<style lang="scss" scoped></style>