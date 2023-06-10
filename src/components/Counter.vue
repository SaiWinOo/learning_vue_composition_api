<template>
  <div class="flex justify-center flex-col items-center">
    <h4 class="font-bold text-3xl text-green-500">{{ message }}</h4>
    <h4 class="font-bold text-3xl text-green-500">{{ intro }}</h4>
    <div>
      {{ count }}
    </div>
    <div>
      <button @click="subtract" class="bg-green-400 py-2 px-5">-</button>
      <button @click="add" class="bg-green-400 py-2 px-5">+</button>
    </div>
  </div>
</template>

<script setup>
import { computed, onMounted, onUnmounted, ref, watch } from 'vue';

const count = ref(0);
const props = defineProps({
  message: String
})
const emit = defineEmits(['sayHello']);
function add() {
  count.value += 1;
}
function subtract() {
  count.value -= 1;
  emit('sayHello');
}

const intro = computed(() => {
  return 'My name is Sai Win Oo and my age is ' + count.value;
})
watch(count, (value) => {
  console.log(value)
})
onMounted(() => {
  console.log('mounted');
})
onUnmounted(() => {
  console.log('unmounted')
})
</script>
