<script setup>
import { ref } from 'vue'

const name = ref('Vishnu K')
const role = ref('Full Stack Developer')
const location = ref('Coimbatore')

const isOnline = ref(true)

const skills = ref([
  'Vue',
  'React',
  'Java',
  'Python'
])

const newSkill = ref('')

function addSkill() {
  if (newSkill.value.trim()) {
    skills.value.push(newSkill.value.trim())
    newSkill.value = ''
  }
}
</script>

<template>
  <div class="container">

    <h1>{{ name }}</h1>

    <h2>{{ role }}</h2>

    <p>{{ location }}</p>

    <p v-if="isOnline">
       Online
    </p>

    <p v-else>
       Offline
    </p>

    <button @click="isOnline = !isOnline">
      Toggle Status
    </button>

    <br><br>

    <input
      v-model="newSkill"
      type="text"
      placeholder="Enter a skill"
    />

    <button
      @click="addSkill"
      :disabled="newSkill === ''"
    >
      Add Skill
    </button>

    <div class="task-container">

      <div
        class="task-card"
        v-for="skill in skills"
        :key="skill"
      >
        <h3>{{ skill }}</h3>
      </div>

    </div>

  </div>
</template>