<script setup>
import { ref } from 'vue'
import '../Styles/Day3.css'

const num1 = ref(0)
const num2 = ref(0)
const sum = ref(0)

function calculate() {
  sum.value = Number(num1.value) + Number(num2.value)
}
</script>

<template>
  <section class="day3-container">

    <h2>Day 3</h2>

    <h1>Enter the numbers:</h1>

    <input
      class="day3-input"
      type="number"
      v-model="num1"
      placeholder="Num 1"
    />

    <input
      class="day3-input"
      type="number"
      v-model="num2"
      placeholder="Num 2"
    />

    <button @click="calculate">
      Calculate
    </button>

    <p class="day3-result">
      Sum: {{ sum }}
    </p>

  </section>
</template>