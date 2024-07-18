<template>
  <DatePicker
    v-model="date1"
    @update:model-value="log($event, 'date only')"
    placeholder="date only"
  />
  <br />
  <DatePicker
    v-model="date2"
    show-time
    @update:model-value="log($event, 'with time')"
    placeholder="with time"
  />
  <br />
  <DatePicker
    v-model="date3"
    show-time
    show-seconds
    @update:model-value="log($event, 'with seconds')"
    placeholder="with seconds"
  />
</template>

<script setup lang="ts">
import DatePicker from "primevue/datepicker";
import { ref } from "vue";

const date1 = ref();
const date2 = ref();
const date3 = ref();

function log(
  date: Date | null,
  type: "date only" | "with time" | "with seconds"
) {
  console.log(type.padEnd(12, " "), date?.toISOString());
}
</script>
