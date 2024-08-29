<script setup lang="ts">
import { ref } from 'vue';

import VueDatePicker from '@vuepic/vue-datepicker';
import '@vuepic/vue-datepicker/dist/main.css'

const date = ref();
</script>

<template>
 <VueDatePicker v-model="date" :enable-time-picker="false" auto-apply>
  <template #input-icon>
            <!-- <img class="input-slot-image" src="/logo.png"/> -->
        </template>
 </VueDatePicker>
</template>

<style>
:root {
  --dp-input-padding: 12px 0px;
}
</style>
