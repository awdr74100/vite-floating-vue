<script setup lang="ts">
// import AtomicSelect from '@/components/atomics/AtomicSelect.vue';
// import AtomicDatePicker from '@/components/atomics/AtomicDatePicker.vue';
// import Banner from '@/assets/img/banner.jpg?format=webp&quality=10&imagetools';

import { useForm, useField, useFieldArray } from '@vorms/core';
import { valibotResolver } from '@vorms/resolvers/valibot';
import * as v from 'valibot';
import AtomicCheckbox from '@/components/atomics/AtomicCheckbox.vue';

import type {InferOutput} from 'valibot'

const schema = v.object({
  // colors: v.pipe(v.array(v.union([v.string(), v.number()])), v.minLength(1)),
  colors: v.pipe(v.array(v.string()), v.minLength(1)),
});

type Schema = InferOutput<typeof schema>

const { handleSubmit, setFieldValue } = useForm<{ colors?:string[] }>({
  reValidateMode: 'change',
  validate: valibotResolver(schema),
  initialValues: {
    colors: [],
  },
  onSubmit(data) {
    console.log(data);
  },
});

const { value, attrs, error } = useField<string[]>('colors')

// const schema = z.object({
//   title: z.string().min(6),
//   users: z.array(
//     z.object({
//       name: z.string().min(3),
//       age: z.number().min(0),
//     }),
//   ),
// });

// const schema = v.object({
//   title: v.pipe(v.string(), v.minLength(6)),
//   users: v.pipe(
//     v.array(
//       v.object({
//         name: v.pipe(v.string(), v.minLength(3)),
//         age: v.pipe(v.number(), v.minValue(0)),
//       }),
//     ),
//     v.minLength(0)
//   ),
// });

// const { handleSubmit, errors } = useForm<v.InferOutput<typeof schema>>({
//   initialValues: {
//     title: '',
//     users: [],
//     // users: [{ age: -1, name: '123' }],
//   },
//   validate: valibotResolver(schema),
//   reValidateMode: 'input',
//   onSubmit(data) {
//     console.log(data);
//   },
// });

// const { attrs, value, error } = useField('title');

// const { fields, append, remove } = useFieldArray<{ name: string; age: number }>('users');
</script>

<template>
  <!-- <h1 class="text-center text-yellow-500">{{ errors }}</h1> -->
  <div class="mx-auto max-w-screen-md">
    <form @submit="handleSubmit">
      <p>{{ value }}</p>
      <p>{{ error }}</p>
      <!-- <AtomicCheckbox name="colors" value="red" />
      <AtomicCheckbox name="colors" value="blue" />
      <AtomicCheckbox name="colors" value="yellow" /> -->
      <div>
        <label for="red">RED</label>
        <input id="red" type="checkbox" value="red" v-model="value" v-bind="attrs" />
      </div>
      <div>
        <label for="blue">BLUE</label>
        <input id="blue" type="checkbox" value="blue" v-model="value" v-bind="attrs" />
      </div>
      <div>
        <label for="purple">PURPLE</label>
        <input id="purple" type="checkbox" value="purple" v-model="value" v-bind="attrs" />
      </div>
      <button type="submit" class="border border-gray-500">SUBMIT</button>
      <button type="button" class="border" @click="setFieldValue('colors', undefined, true)">Set</button>
    </form>
    <!-- <form @submit="handleSubmit">
      <div class="flex flex-col gap-y-4">
        <input type="text" v-model="value" v-bind="attrs" class="border border-gray-400" />
        <span class="text-red-500">{{ error }}</span>
      </div>

      <ul class="flex flex-col gap-4">
        <li v-for="(field, index) in fields" :key="field.key" class="flex flex-col border p-4">
          <pre>{{ field.attrs }}</pre>
          <p>{{ field.key }} {{ index }}</p>
          <button type="button" class="border border-green-400" @click="remove(index)">remove</button>
          <input class="border" v-bind="field.attrs" type="text" v-model="field.value.name" />
          <input
            class="border"
            :name="field.name"
            type="number"
            v-bind="field.attrs"
            v-model.number="field.value.age"
          />
          <span>Value: {{ field.value }}</span>
          <span>Error: {{ field.error }}</span>
        </li>
      </ul>

      <button
        type="button"
        class="bg-purple-500 px-3 py-2"
        @click="append({name: '', age: 1 })"
      >
        Add
      </button>

      <button
        type="button"
        class="bg-red-500 px-3 py-2"
        @click="remove()"
      >
        Clear
      </button>

      <button type="submit" class="bg-green-500 px-3 py-2">Submit</button>
    </form> -->
  </div>
  <!-- <img :src="Banner" />
  <img src="/banner.jpg" />
  <div class="grid min-h-screen w-full auto-rows-max grid-cols-4 gap-4">
    <template v-for="_n in 10" :key="_n">
      <AtomicDatePicker /> -->
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
  <!-- </template> -->
  <!-- lorem2000 -->
  <!-- </div> -->
</template>
