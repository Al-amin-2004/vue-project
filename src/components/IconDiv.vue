<template>
    <div class="mb-3 text-center">
        <div :class="`flex justify-center items-center rounded-lg p-2 ${!title && 'bg-white/20'}`">
        <span v-html="icon"></span>
    </div>
    <p class="text-xs">{{ title }}</p>
    </div>
</template>


<script setup lang="ts">
defineProps<{icon: string,title: string;}>();
</script>

