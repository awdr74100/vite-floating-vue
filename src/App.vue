<script setup lang="ts">
// import AtomicSelect from '@/components/atomics/AtomicSelect.vue';
import AtomicDatePicker from '@/components/atomics/AtomicDatePicker.vue';
</script>

<template>
  <div class="min-h-screen w-full grid grid-cols-4 auto-rows-max gap-4">
    <template v-for="_n in 10" :key="_n">
      <AtomicDatePicker />
      <!-- <h2>123</h2> -->
      <!-- <AtomicSelect
        :options="[
          { label: '你好阿', value: _n ** 2 },
          { label: `${_n ** 3}`, value: _n ** 3 },
          { label: `${_n ** 4}`, value: _n ** 4 },
          { label: `${_n ** 5}`, value: _n ** 5 },
          { label: `${_n ** 6}`, value: _n ** 6 },
          { label: `${_n ** 7}`, value: _n ** 7 },
        ]"
      /> -->
    </template>
    <!-- lorem2000 -->
  </div>
</template>
