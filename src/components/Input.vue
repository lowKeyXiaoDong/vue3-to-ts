<template>
    <div>
        <input :value="modelValue" @input="onInput" v-bind="$attrs" />
    </div>
</template>

<script lang="ts">
export default {
    inheritAttrs: false
}
</script>
<script setup lang="ts">
import { emitter } from '../composables/useEmitter'


// 输入内容
defineProps({
    modelValue: {
        type: String,
        default: ''
    }
})

// 输出事件
const emit = defineEmits<{
    (e: 'update:model-value', value: string): void
}>()

function onInput(e: Event) {
    const inp = e.target as HTMLInputElement
    emit('update:model-value', inp.value)

    emitter.emit('validate')
}
</script>

<style scoped>
</style>