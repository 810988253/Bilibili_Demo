<template>
  <van-tabs v-model:active="active">
    <van-tab v-for="item in list" :key="item.id" :title="item.text"></van-tab>
  </van-tabs>
</template>

<script setup lang="ts">
  import axios from 'axios'
  import { ref } from 'vue'

  interface INavItem {
    id: string
    text: string
  }

  const active = ref(0)
  //频道数据
  const list = ref<INavItem[]>([])

  axios({
    url: '/navList',
    method: 'get'
  }).then(res => {
    console.log(res)
    list.value = res.data.result
  })
</script>
