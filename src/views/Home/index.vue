<script setup lang="ts">
  import AppHeader from '@/components/appHeader.vue'
  import HomeChannel from './component/homeChannel.vue'
</script>

<template>
  <!-- 头部组建 -->
  <AppHeader />
  <!-- 频道组建 -->
  <HomeChannel />
  <router-link to="/video/1"></router-link>
</template>
