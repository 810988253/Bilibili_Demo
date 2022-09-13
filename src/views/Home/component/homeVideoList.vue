<template>
  <div class="list">
    <appVideoItem v-for="item in list" :key="item.id" :video="item" />
  </div>
</template>

<script setup lang="ts">
  import appVideoItem from '@/components/appVideoItem.vue'
  import { ref } from 'vue'
  import axios from 'axios'

  interface IVideoItem {
    id: number
    imgSrc: string
    desc: string
    playCount: string
    commentCount: string
    videoSrc: string
  }
  const list = ref<IVideoItem[]>([])
  axios({
    url: '/videosList',
    method: 'get'
  }).then(res => {
    list.value = res.data.result
  })
</script>

<style lang="less">
  .list {
    display: flex;
    flex-wrap: wrap;
    padding: 0 1vw;
  }
</style>
