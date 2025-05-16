<template>
  <v-app>
    <Sidebar />
    <v-main>
      <v-container fluid>
        <router-view />
        <Main />
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import Main from './components/Main.vue';
import Sidebar from './components/sidebar/SideBar.vue'
</script>
