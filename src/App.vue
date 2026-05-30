<script setup>
import './style.css'
import Day2 from './components/Day2.vue'
import Day3 from './components/Day3.vue'
import Day4 from './components/Temp.vue'
import MySkills from './components/MySkills.vue'
const today = new Date().toDateString()
</script>

<template>
  <div class="container">
    <h1>Vishnu K</h1>
    <h2>Full Stack Developer</h2>
    <p>Coimbatore</p>
    <p>{{ today }}</p>
    <Day2 />
    <Day3/>
    <Day4/>
    <MySkills />
  </div>
</template>