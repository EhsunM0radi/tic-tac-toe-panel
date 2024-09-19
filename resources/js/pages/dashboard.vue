<script setup>
import CustomFixedHeaderTable from '@/components/tables/CustomFixedHeaderTable.vue'
import axios from 'axios'
import { onMounted, ref } from 'vue'


const data = ref([])

const columns = [
  { name: 'id', label: 'ID' },
  { name: 'token', label: 'Token' },
]

// دریافت داده‌ها از API لاراول
onMounted(async () => {
  try {
    const response = await axios.get('http://tic-tac-toe-api.test/api/game-tokens')

    data.value = response.data
  } catch (error) {
    console.error('Error fetching data:', error)
  }
})
</script>

<template>
  <VRow class="match-height">
    <VCol cols="12">
      <VCard title="Game Tokens">
        <CustomFixedHeaderTable
          :columns="columns"
          :data="data"
        />
      </VCard>
    </VCol>
  </VRow>
</template>
