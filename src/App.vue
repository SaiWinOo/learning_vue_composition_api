
<template>
  <button @click="toggleSetupCounter" class="bg-green-500 py-2 px-5">Toggle Setup Counter</button>
  <button @click="toggleSecondCounter" class="bg-green-500 py-2 px-5">Toggle Second Counter</button>

  <div class="flex justify-center items-center h-screen flex-col">

    <div class="flex justify-center items-center">
      <Counter v-if="showSetupCounter" message="This is message from app" @sayHello="sayHello" />
    </div>

    <div class="flex justify-center items-center">
      <SecondCount message="This is message from app" v-if="showSecondCounter" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Counter from './components/Counter.vue';
import SecondCount from './components/SecondCount.vue';
const showSetupCounter = ref(true);
const showSecondCounter = ref(true);

const toggleSetupCounter = () => {
  showSetupCounter.value = !showSetupCounter.value;
}
const toggleSecondCounter = () => {
  showSecondCounter.value = !showSecondCounter.value;
}
function sayHello() {
  console.log('I am hello from app')
}

</script>
