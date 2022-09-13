<script setup lang="ts">
  import AppHeader from '@/components/appHeader.vue'
  import HomeChannel from './component/homeChannel.vue'
  import HomeSwiper from './component/homeSwiper.vue'
  import HomeVideoList from './component/homeVideoList.vue'
</script>

<template>
  <!-- 头部组件 -->
  <AppHeader />
  <!-- 频道组件 -->
  <HomeChannel />
  <!-- 轮播组件 -->
  <HomeSwiper />
  <!-- 首页视频组件 -->
  <HomeVideoList />
  <router-link to="/video/1"></router-link>
</template>
