<template>
  <div class="flex flex-col p-8">
    <input
      type="text"
      class="rounded border-2 border-gray-200 w-full"
      placeholder="Search for Meals"
    >
    <div class="flex gap-2 mt-2 justify-center">
      <router-link
        v-for="letter of letters"
        :to="{ name: 'byLetter', params: { letter } }"
        :key="letter"
        :letter="letter"
        class="btn"
      >
        {{ letter }}
      </router-link>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';
import axiosClient from '../axiosClient.js';

const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('');

onMounted(async () => {
  const response = await axiosClient.get('/list.php?i=list')
  console.log(response.data);
});
</script>
