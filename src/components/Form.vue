<template>
    <form>
        <slot></slot>
    </form>
</template>

<script setup lang="ts">
import { PropType } from "vue";
import { Rules } from 'async-validator'

defineProps({
    model: { type: Object, required: true },
    rules: { type: Object as PropType<Rules> }
})

// 定义输出
function validator() {
    console.log('validator');
}

defineExpose({
    validator
})
</script>

<style lang="less" scoped>
</style>