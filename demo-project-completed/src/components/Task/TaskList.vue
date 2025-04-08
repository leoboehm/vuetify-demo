<template>
  <v-row>
    <v-col v-for="task in tasks" :key="task.id" cols="12">
      <TaskCard :task="task" @toggle-task="$emit('toggle-task', task.id)" />
    </v-col>
  </v-row>
</template>

<script setup>
import TaskCard from "@/components/Task/TaskCard.vue";

defineProps({ tasks: Array });
</script>
