<script setup>
import { defineProps } from 'vue'

// تعریف props برای دریافت داده‌ها و ستون‌ها
const props = defineProps({
  columns: {
    type: Array,
    required: true,
  },
  data: {
    type: Array,
    required: true,
  },
})
</script>

<template>
  <VTable
    height="500"
    fixed-header
  >
    <thead>
      <tr>
        <th
          v-for="column in columns"
          :key="column.name"
          class="text-center text-uppercase"
        >
          {{ column.label }}
        </th>
      </tr>
    </thead>
    <tbody>
      <tr
        v-for="item in data"
        :key="item.id"
      >
        <td
          v-for="column in columns"
          :key="column.name"
          class="text-center"
        >
          {{ item[column.name] }}
        </td>
      </tr>
    </tbody>
  </VTable>
</template>
