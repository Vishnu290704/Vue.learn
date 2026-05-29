<script setup>
  import {ref} from 'vue';
  const num1 = ref(0);
  const num2 = ref(0);
  const sum = ref(0);
  function calculate(){
    sum.value = Number(num1.value) + Number(num2.value);
  }
</script>
<template>
  <div>
    <h1>Enter the numbers:</h1>
    <input type="number" 
    v-model="num1"
    placeholder="Num 1" />
    <br><br>
    <input type="number"
    v-model="num2"
    placeholder="num2"/>
    <br><br>
    <button @click="calculate">Calculate</button>

    <p>Sum: {{ sum }}</p>
  </div>
</template>