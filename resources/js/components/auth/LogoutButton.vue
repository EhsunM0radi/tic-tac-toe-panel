<script setup>
import axios from 'axios'
import { useRouter } from 'vue-router'

// توکن احراز هویت را از localStorage می‌گیریم
const token = localStorage.getItem('accessToken')
const router = useRouter()

const logout = async () => {
  try {
    // ارسال درخواست خروج به API
    await axios.get('http://tic-tac-toe-panel.test/api/auth/logout', {
      headers: {
        Accept: 'application/json',
        Authorization: `Bearer ${token}`,
      },
    })
    
    // حذف توکن از localStorage
    localStorage.removeItem('accessToken')
    
    // هدایت به صفحه ورود
    router.push('/login')
  } catch (error) {
    console.error('Logout failed:', error)
  }
}
</script>

<template>
  <VListItem @click="logout">
    <template #prepend>
      <VIcon
        class="me-2"
        icon="ri-logout-box-r-line"
        size="22"
      />
    </template>
    <VListItemTitle>Logout</VListItemTitle>
  </VListItem>
</template>
