<template>
  <v-app>
    <NavBar @toggleTheme="toggleTheme" />

    <v-main>
      <v-container fluid>
        <HelloWorld />
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import { useTheme } from "vuetify";
import NavBar from "@/components/NavBar.vue";
import HelloWorld from "@/pages/ToDo.vue";

const theme = useTheme();

function toggleTheme() {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}
</script>
