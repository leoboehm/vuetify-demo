<template>
  <v-container>
    <h2 class="mb-2 d-flex justify-space-between align-center">
      Open Tasks
      <TaskDialog @add-task="addTask" />
    </h2>
    <v-progress-linear
      :model-value="completionRate"
      height="40"
      color="green"
      class="mb-6"
    >
      <strong>Tasks completed: {{ completionRate }}%</strong>
    </v-progress-linear>
    <TaskList :tasks="openTasks" @toggle-task="markAsDone" />

    <v-divider :thickness="4" class="mt-10" color="secondary"></v-divider>

    <h3 class="mt-6 mb-2">Completed Tasks</h3>
    <TaskList :tasks="doneTasks" @toggle-task="removeTask" />
  </v-container>
</template>

<script setup>
import { ref, computed, watch } from "vue";
import TaskDialog from "@/components/Task/TaskDialog.vue";
import TaskList from "@/components/Task/TaskList.vue";

const tasks = ref(loadTasks());

const openTasks = computed(() => tasks.value.filter((item) => !item.done));
const doneTasks = computed(() => tasks.value.filter((item) => item.done));
const completionRate = computed(() =>
  tasks.value.length === 0
    ? 0
    : Math.round((doneTasks.value.length / tasks.value.length) * 100)
);

function addTask(title, text) {
  tasks.value.push({ id: Date.now(), title, text, done: false });
  saveTasks();
}

function markAsDone(id) {
  const task = tasks.value.find((item) => item.id === id);
  if (task) task.done = true;
  saveTasks();
}

function removeTask(id) {
  tasks.value = tasks.value.filter((item) => item.id !== id);
  saveTasks();
}

function saveTasks() {
  localStorage.setItem("tasks", JSON.stringify(tasks.value));
}

function loadTasks() {
  return JSON.parse(localStorage.getItem("tasks") || "[]");
}

watch(tasks, saveTasks, { deep: true });
</script>
