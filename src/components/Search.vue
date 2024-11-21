<script setup>
  import { defineProps } from "vue"
  import {ref} from "vue"

  const props = defineProps({
    listContacts: {
      type: Array,
      default: []
    }
  })

  const bgBtn = ref("blue")

  const isFocus = () => {
    bgBtn.value = "red";
  }

</script>

<template>
    <div class="flex gap-4 my-4">
      <input
        type="text"
        class="block flex-1 border-0 bg-white py-1.5 pl-1 text-black placeholder:text-gray-400 focus:ring-0 sm:text-sm/6 rounded-full"
        placeholder="Search Name"
        @focus="isFocus"
      >
      <button
        class="bg-blue-500 rounded-full px-4 py-2"
        :style="{ backgroundColor: bgBtn }"
      >
        Search
      </button>
    </div>
</template>