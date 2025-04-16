<template>
  <!-- TODO: Implement main page! -->
</template>

<script setup>
import { ref, computed, watch } from "vue";

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
