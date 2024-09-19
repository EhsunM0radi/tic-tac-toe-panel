<script setup>
import VerticalNavLink from '@layouts/components/VerticalNavLink.vue'
</script>

<template>
  <!-- 👉 Dashboards -->
  
  <VerticalNavLink
    :item="{
      title: 'List',
      icon: 'ri-home-smile-line',
      to: '/dashboard',
    }"
  /> 

  <!-- 👉 Front Pages -->
  
  <!-- 👉 Apps & Pages -->
  
  <!-- 👉 User Interface -->
  
  <!-- 👉 Forms & Tables -->
  
  <VerticalNavLink
    :item="{
      title: 'Tables',
      icon: 'ri-table-alt-line',
      to: '/tables',
    }"
  />

  <!-- 👉 Others -->
</template>
