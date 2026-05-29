<script setup>
import './style.css'
import MySkills from './components/MySkills.vue'

const today = new Date().toDateString()
</script>

<template>
  <div class="container">

    <h1>Vishnu K</h1>
    <h2>Full Stack Developer</h2>
    <p>Coimbatore</p>
    <p>{{ today }}</p>

    <MySkills />

  </div>
</template>