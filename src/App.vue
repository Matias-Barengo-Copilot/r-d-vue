<script setup>
import Search from "./components/Search.vue"
import Agenda from "./components/Agenda.vue"
import { ref } from "vue"
import { getAllContacts } from "./services/apiContacts.js"

const listContacts = ref(getAllContacts())

const title = "Mi agenda - Lista de contactos"

const clearList = () => {
  listContacts.value = []
}

</script>

<template>
  <div class="flex items-center flex-col p-5">
    <h1 class="text-3xl m-4">{{title}}</h1>
    <Search
    :listContacts="listContacts"
    />
    <Agenda 
      title="Mi Agenda"
      :listContacts="listContacts"
    />
    <div>
      <button
        @click="clearList()"
        class="bg-blue-500 rounded-full px-4 py-2"
      >
        Limpiar lista
      </button>
    </div>
  </div>
</template>
