<script setup lang="ts">
import { Dropdown } from 'floating-vue';

import 'floating-vue/dist/style.css';

defineProps<{
  options: {
    label: string;
    value: number;
  }[];
}>();
</script>

<template>
  <div class="relative">
    <Dropdown :auto-size="true" :distance="6">
      <div class="flex min-h-12 text-gray-700 min-w-20 items-center px-[13px] bg-white border border-gray-700">
        {{ '你好阿' }}
      </div>
      <template #popper="{ hide }">
        <ul class="flex max-h-[168px] w-full flex-col [&::-webkit-scrollbar]:w-2 overflow-y-auto [&::-webkit-scrollbar-thumb]:bg-gray-700">
          <li
            class="w-full bg-red-400 px-4 py-4 text-white hover:bg-red-300"
            v-for="option in options"
            :key="option.value"
            @click="hide"
          >
            {{ option.label }}
          </li>
        </ul>
      </template>
    </Dropdown>
  </div>
</template>

<style>
.v-popper__inner {
  @apply !border-0;
}

/* .v-popper__inner::-webkit-scrollbar { */
  /* @apply w-2; */
/* } */

/* .v-popper__inner::-webkit-scrollbar-thumb { */
  /* @apply rounded-md;
  @apply bg-gray-500; */
  /* -webkit-border-radius: 6px; */
  /* @apply rounded-md; */
/* } */

/* .v-popper__inner::-webkit-scrollbar-track {
  @apply bg-red-400;
  @apply rounded-r-md;
} */
</style>
