<template>
  <van-swipe class="my-swipe" :autoplay="3000" indicator-color="white">
    <van-swipe-item v-for="item in list" :key="item.imgSrc">
      <img :src="item.imgSrc" />
    </van-swipe-item>
  </van-swipe>
</template>

<script setup lang="ts">
  import axios from 'axios'
  import { ref } from 'vue'

  interface ISwiperList {
    imgSrc: string
    link: string
  }
  const list = ref<ISwiperList[]>([])

  axios({
    url: '/swiperList',
    method: 'get'
  }).then(res => {
    list.value = res.data.result
  })
</script>

<style scoped>
  .my-swipe .van-swipe-item {
    color: #fff;
    font-size: 20px;
    line-height: 150px;
    text-align: center;
  }
</style>
