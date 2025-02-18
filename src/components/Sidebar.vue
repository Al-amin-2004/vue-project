<script setup lang="ts">
import IconDiv from "./IconDiv.vue";
import Search from "./icons/Search.vue";
import Link from "./icons/Link.vue";
import History from "./icons/History.vue";
</script>



<template>
  <aside
    class="p-4 max-w-20 h-full bg-gray-900 text-white border-e border-gray-400"
  >
    <IconDiv :label-icon="Search" />
    <IconDiv :label-icon="Link" />
    <IconDiv :label-icon="History" title="Explore" />
  </aside>
</template>

