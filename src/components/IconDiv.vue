<script setup lang="ts">
import type { Component, PropType } from 'vue';

defineProps({
  labelIcon: {
    type: Object as PropType<Component>,
    required: false,
  },
  
  title:String,
});


</script>

<template>
  <div class="mb-3 text-center">
    <div
      class="flex justify-center items-center rounded-lg p-3"
    >
    <component v-if="labelIcon" :is="labelIcon"/>

    </div>
    <p class="text-xs">{{ title }}</p>
  </div>
</template>
