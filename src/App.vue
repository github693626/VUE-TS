<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { ref } from "vue";
import Job from "@/types/Job";
import OrderTrem from "@/types/OrderTrem";
import JobsList from "@/components/jobsList.vue";

const name = ref<String>("leo");
const changeName = (newName: String) => {
  name.value = newName;
};

const age = ref<Number | String>(30);
const changeAge = (newAge: Number | String) => {
  age.value = newAge;
};

const jobs = ref<Job[]>([
  {
    title: "F2E工程師",
    location: "台北市",
    salary: 50000,
    id: "job.01",
  },
  {
    title: ".Net工程師",
    location: "台北市",
    salary: 40000,
    id: "job.02",
  },
]);
const order = ref<OrderTrem>("title");
const handleClick = (trem: OrderTrem) => {
  order.value = trem;
};
</script>

<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3 + Vite" /> -->
  <p>{{ name }} - {{ age }}</p>
  <button @click="changeName('lisa')">Change Name</button>
  <button @click="changeAge(20)">Change Age</button>
  <p>{{ jobs[0].location }}</p>

  <button @click="handleClick('title')">order by title</button>
  <button @click="handleClick('salary')">order by salary</button>
  <button @click="handleClick('location')">order by location</button>

  <JobsList :jobs="jobs" :order="order" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
