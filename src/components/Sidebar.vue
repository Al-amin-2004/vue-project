<script setup lang="ts">
import { SidebarDatas } from "./data/data";
import Search from "./icons/Search.vue";
import Link from "./icons/Link.vue";
import Gear from "./icons/Gear.vue";
import User from "./icons/User.vue";
import { ref } from "vue";


let active = ref<number>(1);

function MyFunc(idx: number): void {
  active.value = idx;
}
</script>



<template>
  <aside class="px-4 py-2 max-w-20 h-full bg-gray-900 text-slate-300 border-e border-gray-400 flex flex-col justify-between">
    <div class="flex flex-col gap-2.5 pb-4 border-b border-slate-200/40">

      <div class="space-y-2">
        <img src="/bullx_logo.png" alt="bullx_logo">
        <img src="/angry-horse.png" alt="angry-horse">
      </div>

      <div class="flex flex-col items-center gap-2">
        <div class="text-center inline-block rounded-lg p-2 bg-white/10 cursor-pointer">
          <component v-if="Search" :is="Search" class="size-5" />
        </div>
        <div class="text-center inline-block rounded-lg p-2.5 bg-white/10 cursor-pointer mb-2">
          <component v-if="Link" :is="Link" class="size-4" />
        </div>
      </div>


      <div v-for="(item) in SidebarDatas" :key="item.id" v-on:click="MyFunc(item.id)"
        class="flex flex-col items-center cursor-pointer gap-1" :class="{ 'text-green-400': item.id === active }" :title="item.label">
        <component v-if="item.icon" :is="item.icon" class="size-5" />
        <p class="text-xs text-center">{{ item.label }}</p>
      </div>
    </div>



    <div class="space-y-4">
      <div class="p-1.5 border border-green-400 rounded-full">
        <img src="/bullx_logo.png" alt="bullx_logo">
      </div>

      <div class="flex flex-col items-center cursor-pointer gap-1" title="Settings">
        <component v-if="Gear" :is="Gear" />
        <p class="text-xs text-center">Settings</p>
      </div>
      <div class="flex flex-col items-center cursor-pointer gap-1" title="Accounts">
        <component v-if="User" :is="User" />
        <p class="text-xs text-center">Accounts</p>
      </div>
    </div>
  </aside>
</template>
