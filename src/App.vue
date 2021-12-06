<template>
  <!-- <Comp :title-info="{ id: 2, name: 'vue to ts'}" />
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" /> -->
  <Form :model="model">
    <FormItem label="用户名" prop="username">
      <Input v-model="model.username" type="text" />
    </FormItem>
  </Form>
</template>

<script setup lang="ts">
// import HelloWorld from './components/HelloWorld.vue'
// import Comp from './components/Comp.vue'
import { reactive } from 'vue'
import Form from '@/components/Form.vue'
import FormItem from '@/components/FormItem.vue'
import Input from '@/components/Input.vue'

const model = reactive({
  username: 'aaa'
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
