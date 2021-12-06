<template>
    <div @click="addCount">{{ count }}</div>
    <div>
        {{ doubleCount }}
        <input type="text" v-model="todoName" @keydown.enter="addTodo" />
    </div>
    <div v-for="todo in todos">{{ todo.name }}</div>
    <div>{{ titleInfo.name }}</div>
</template>

<script lang="ts" setup>
import { ref, computed } from 'vue'
import type { PropType } from 'vue'

interface Todos {
    id: number,
    name: string
}

interface TitleInfo extends Todos {

}

defineProps({
    titleInfo: {
        type: Object as PropType<TitleInfo>,
        required: true
    }
})

const count = ref<number>(0)
const doubleCount = computed(() => count.value * 2)
function addCount(): void {
    count.value++
}

const todoName = ref<string>('')
const todos = ref([] as Todos[])
function addTodo() {
    todos.value.push({
        id: todos.value.length + 1,
        name: todoName.value
    })
    todoName.value = ''
}
</script>

<style lang="css">
.name {
    color: red;
}
</style>