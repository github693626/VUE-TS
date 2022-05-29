<template>
  <div class="job-list">
    <p>order by {{ order }}</p>
    <ul>
      <li v-for="job in jobs" :key="job['id']">
        <h2>{{ job["title"] }} in {{ job["location"] }}</h2>
        <div class="salary">${{ job["salary"] }}</div>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { PropType, onMounted } from "vue";
import Job from "@/types/Job";
import OrderTrem from "@/types/OrderTrem";

// "@/types/Job
const props = defineProps({
  jobs: {
    required: true,
    type: Array as PropType<Job[]>,
  },
  order: {
    required: true,
    type: String as PropType<OrderTrem>,
  },
});

onMounted(() => {
  console.log(props.order);
});
</script>

<style scoped></style>
