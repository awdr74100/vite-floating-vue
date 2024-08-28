<script setup lang="ts">
import { Dropdown } from 'floating-vue'

import 'floating-vue/dist/style.css'
</script>

<template>
  <Dropdown
  :shown="true"
  :auto-size="true"
  :distance="6"
>
 <div class="min-w-20 min-h-12 bg-red-500 text-white flex items-center justify-center">{{ 'good' }}</div>
 <template #popper="{ hide }">

  <ul class="w-full flex flex-col max-h-[120px]">
    <li class="w-full bg-red-400 hover:bg-red-300 text-white" v-for="n in 10" :key="n" @click="hide">
      {{ n }}
    </li>
  </ul>
 </template>
</Dropdown>
</template>
