<script setup>
const skills = [
  'Java',
  'Python',
  'Vue.js'
]
</script>

<template>
  <div class="task-container">
    <div class="task-card" v-for="skill in skills" :key="skill">
      <h2>{{ skill }}</h2>
    </div>
  </div>
</template>