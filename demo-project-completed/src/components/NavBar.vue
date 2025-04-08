<template>
  <v-app-bar color="secondary">
    <v-toolbar-title>
      <v-icon class="mr-2">mdi-format-list-checkbox</v-icon>
      My ToDo List
    </v-toolbar-title>
    <v-spacer />
    <v-tooltip text="Toggle dark/light theme">
      <template v-slot:activator="{ props }">
        <v-btn icon @click="$emit('toggleTheme')" v-bind="props">
          <v-icon>mdi-brightness-6</v-icon>
        </v-btn>
      </template>
    </v-tooltip>
  </v-app-bar>
</template>
