<script setup>
import { ref } from 'vue'
import { sayHello } from '../api/hello'

const message = ref('音乐app')
const count = ref(0)

const hi = () => {
  sayHello().then(res => {
    console.log(res)
  })
  message.value = '服务器已启动'
}
</script>

<template>
  {{ message }}
  <br>
  <q-btn color="primary" @click="count++">点击次数{{ count }}</q-btn>
  <br>
  <br>
  <q-btn color="primary" @click="hi">请求接口</q-btn>
  
</template>

<style scoped>

</style>
