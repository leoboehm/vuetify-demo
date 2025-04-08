<template>
  <v-card elevation="2" :color="task.done ? 'grey' : 'secondary'">
    <v-card-title class="d-flex justify-space-between align-center">
      {{ task.title }}
      <v-btn
        icon
        :color="task.done ? 'red' : 'green'"
        @click="$emit('toggle-task')"
      >
        <v-icon>{{ task.done ? "mdi-delete" : "mdi-check" }}</v-icon>
      </v-btn>
    </v-card-title>
    <v-card-text>{{ task.text }}</v-card-text>
  </v-card>
</template>

<script setup>
defineProps({ task: Object });
</script>
