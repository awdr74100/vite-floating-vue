<script setup lang="ts">
import { useField } from '@vorms/core'
import { toRef } from 'vue';



type AtomicCheckboxProps = {
  name: string
  value: string | number
}

const props = withDefaults(defineProps<AtomicCheckboxProps>(), {})

const nameRef = toRef(props, 'name')

const { value:checkValue,attrs,error } = useField(nameRef)
</script>

<template>
  <div>
      <label :for="name">{{ name.toLocaleUpperCase() }}</label>
      <input :id="name" type="checkbox" :value="value" v-model="checkValue" v-bind="attrs">
      <p>{{ error }}</p>
    </div>
</template>
