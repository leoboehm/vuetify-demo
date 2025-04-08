<template>
  <div>
    <v-btn
      color="secondary"
      @click="dialog = true"
      class="mb-4"
      prepend-icon="mdi-plus"
    >
      Add Task
    </v-btn>
    <v-dialog v-model="dialog" persistent max-width="400px">
      <v-card>
        <v-card-title>Add New Task</v-card-title>
        <v-card-text>
          <v-text-field v-model="title" label="Task" autofocus />
          <v-text-field v-model="text" label="Description (Optional)" />
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn text @click="dialog = false">Cancel</v-btn>
          <v-btn color="success" @click="addTask">Add</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
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
