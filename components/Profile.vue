<script setup lang="ts">
import { defineProps, ref } from 'vue'

const props = defineProps({
  name: {
    type: String,
  },
  role: {
    type: String
  },
  github: {
    type: String
  },
  country: {
    type: String
  }
})
const gh = "https://github.com/"+props.github
const img = "kedro-team/"+props.name.toString().replace('\s+', '_').toLowerCase()+".png";
</script>

<template>

<div class="w-5em shadow-lg bg-gradient-to-tr from-gray-50 to-gray-100 border border-gray-200 border-opacity-100 rounded-lg -mt-3">
    <div class="relative p-2 mt-2">
        <span class="absolute -top-1.5 -right-0.5 text-sm"><a :href="gh" target="_blank" class="icon-btn !border-none"> <carbon-logo-github/></a></span>
        <img 
            class="w-12 h-12 rounded-full mx-auto border border-blue-400 border-1 border-opacity-100" 
            :src="img" 
            :alt=props.name
            hover="animate-spin"
        > 
          <p class="text-0.8em text-center">{{name}}<br></p>
          <p class="text-0.6em text-center font-bold">{{role}}</p>
          <p class="text-0.6em text-center">{{country}}</p>
    </div>
</div>

</template>