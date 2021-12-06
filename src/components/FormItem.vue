<template>
    <div>
        <label v-if="label">{{ label }}</label>
        <slot></slot>

        <p v-if="error">{{ error }}</p>
    </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from "vue";
import { emitter } from "../composables/useEmitter";

interface Props {
    label?: string,
    prop?: string
}

withDefaults(defineProps<Props>(), { label: '', prop: '' })

const error = ref<string>('')

onMounted(() => {
    emitter.on('validate', () => {
        validate()
    })
})

function validate() {
    console.log('validate');
    
}
</script>

<style scoped>
</style>