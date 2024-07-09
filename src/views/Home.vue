<template>
  <h1 class="bg-blue-100">{{ meals }}</h1>
</template>

<script setup>
import { computed } from 'vue';
import store from '../store/index.js';

const meals = computed(() => store.state.meals);
</script>
