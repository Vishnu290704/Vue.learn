<script setup>
import '../Styles/Day6.css'
import { reactive } from 'vue'

const form = reactive({
  name: '',
  email: '',
  gender: '',
  country: '',
  agree: false
})

function submitForm() {
  console.log(form)

  alert(`
Name: ${form.name}
Email: ${form.email}
Gender: ${form.gender}
Country: ${form.country}
`)
}
</script>

<template>
  <div class="day6-container">

    <div class="day6-login-card">

      <form @submit.prevent="submitForm">

        <h2 class="day6-title">
          Student Registration
        </h2>

        <input
          class="day6-input"
          v-model="form.name"
          placeholder="Name"
        >

        <input
          class="day6-input"
          v-model="form.email"
          placeholder="Email"
        >

        <label>
          <input
            type="radio"
            value="Male"
            v-model="form.gender"
          >
          Male
        </label>

        <label>
          <input
            type="radio"
            value="Female"
            v-model="form.gender"
          >
          Female
        </label>

        <br><br>

        <select
          class="day6-input"
          v-model="form.country"
        >
          <option value="">
            Select Country
          </option>

          <option>
            India
          </option>

          <option>
            Germany
          </option>
        </select>

        <br><br>

        <label>
          <input
            type="checkbox"
            v-model="form.agree"
          >
          Accept Terms
        </label>

        <br><br>

        <button
          class="day6-button"
          type="submit"
        >
          Submit
        </button>

      </form>

    </div>

  </div>
</template>