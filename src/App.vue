<script setup>
import {RouterView } from 'vue-router'

</script>

<template>
  <div class="flex justify-center items-center">
<router-link to="/" class="text-cnter text-xl mx-4 text-green-700 transition-all duration-500 hover:text-green-900 font-bold">Home</router-link>
<router-link to="/about" class="text-cnter text-xl font-bold mx-4 text-green-700 transition-all duration-500 hover:text-green-900">About</router-link>
  </div>

  <RouterView />
</template>

