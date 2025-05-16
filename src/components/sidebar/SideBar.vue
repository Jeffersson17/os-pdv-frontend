<template>
  <v-app>
    <!-- Sidebar -->
    <v-navigation-drawer id="sidebar" app permanent width="200" color="white">
      <!-- Conteúdo da sidebar -->
      <v-img
        :width="110"
        src="https://imgs.search.brave.com/2lBZ6hbJO_8Wssoo5x5cybbt6cr0tn7w2PTjcd7Ij4E/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly9jYW1v/LmdpdGh1YnVzZXJj/b250ZW50LmNvbS9h/YWZkY2NjYzEzNjcz/YTk1ZWVlNzE4MTkw/NDVlMTFjNWE2MWEx/ZDU2MDEyOWZjM2M5/YWZmZDQ2Y2RjNWMz/YjliLzY4NzQ3NDcw/NzMzYTJmMmY2MzY0/NmUyZTc2NzU2NTc0/Njk2Njc5NmE3MzJl/NjM2ZjZkMmY2OTZk/NjE2NzY1NzMyZjZj/NmY2NzZmNzMyZjZj/NmY2NzZmMmU3Mzc2/Njc"
        class="my-4 mx-auto"
      ></v-img>
      <v-list nav dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          :title="item.title"
          :prepend-icon="item.icon"
          class="rounded-lg"
          active-class="bg-white"
        />
      </v-list>
    </v-navigation-drawer>
    <!-- NAVBAR -->
    <v-app-bar app flat color="transparent" class="px-3">
      <v-row class="pa-3" align="center" justify="end">
        <v-text-field
          v-model="search"
          label="Buscar"
          variant="underlined"
          hide-details
          density="compact"
          class="mr-2"
          style="max-width: 200px"
        />
        <v-btn icon @click="performSearch">
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
      </v-row>
    </v-app-bar>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'

const items = [
  { title: 'Home', icon: 'mdi-home', to: '/' },
  { title: 'Usuários', icon: 'mdi-account', to: '/users' },
  { title: 'Empresas', icon: 'mdi-domain', to: '/reports' },
]

const search = ref('')
const performSearch = () => {
  console.log('Buscando por:', search.value)
  // aqui você pode disparar uma requisição, ou chamar um método de filtro etc.
}
</script>

<style scoped>

</style>
