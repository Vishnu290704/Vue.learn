<script setup>
import { ref, computed, watch, reactive, watchEffect} from 'vue'
const firstname = ref("vishnu");
const lastname = ref("k");
const mark = ref(92)

const student = reactive({
  city: "coimbatore",
  age: "21"
})

const fullname = computed(() => {
  console.log("write the first name: ");
  return `${firstname.value} ${lastname.value}`
})

const grade = computed(() => {
  if (mark.value >= 90) return "A";
  if (mark.value >= 80) return "B";
  return "try again";
})

watch(mark, (newVal, oldVal) => {
  console.log(`New mark: from ${oldVal} ${newVal}`)
})

watch(
  [firstname, lastname],
  ([newFirst, newLast], [oldFirst, oldLast]) => {
    console.log(`Name changed from ${oldFirst} ${oldLast} to ${newFirst} ${newLast}`)
  })
  watch(
  student,
  () => {
    console.log("Student object changed");
  },
  { deep: true }
);
watch(
  mark,
  () => {
    console.log("Immediate Watch Running");
  },
  { immediate: true }
);
watch(
  mark,
  () => {
    console.log("DOM Updated");
  },
  { flush: "post" }
);
watchEffect(() => {
  console.log(`Student: ${fullname.value} | Marks: ${mark.value}`);
});
watch([firstname, lastname, mark], () => {
  localStorage.setItem(
    "studentData",
    JSON.stringify({
      firstName: firstname.value,
      lastName: lastname.value,
      marks: mark.value,
    })
  );
});
const savedData = localStorage.getItem("studentData");

if (savedData) {
  const data = JSON.parse(savedData);

  firstname.value = data.firstName;
  lastname.value = data.lastName;
  mark.value = data.marks;
}
</script>

<template>
  <div>
    <h2>Full Name : {{ fullname }}</h2>

    <h2>Marks : {{ mark }}</h2>

    <h2>Grade : {{ grade }}</h2>

    <h2>City : {{ student.city }}</h2>


    <button @click="student.city = 'Hyderabad'">
      Change City
    </button>
  </div>
</template>