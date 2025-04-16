<template>
  <!-- TODO: Implement dialog to add tasks! -->
</template>

<script setup>
import { ref } from "vue";
const dialog = ref(false);
const title = ref("");
const text = ref("");
const emit = defineEmits(["add-task"]);

function addTask() {
  if (title.value.trim()) {
    emit("add-task", title.value.trim(), text.value.trim());
    title.value = "";
    text.value = "";
    dialog.value = false;
  }
}
</script>
