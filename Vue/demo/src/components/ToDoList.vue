<script setup>
/**
 * @name: ToDoList
 * @description: This component is a demo for my learning outcome.
 * @author: Ruoxi Cao
 * @date: 2025-5-26
 */
import { ref, computed } from 'vue';

let id = 0;
/**
 * 所有待定项
 * @type {ref<[{ id: number; text: string; done: boolean }]>} 
 */
const todos = ref([
    { id: id++, text: 'Learn HTML', done:false },
    { id: id++, text: 'Learn Javascript', done:false },
    { id: id++, text: 'Learn Vue', done:false }
])



// ------------------------ 增加事项 ------------------------
const newTodo = ref('') // 接收用户输入的待定项

/** 增加待定项 */
function addTodo() {
    todos.value.push({ id: id++, text: newTodo.value })
    newTodo.value = '' // 清空输入
}

// ------------------------ 删除事项 ------------------------
/** 删除指定待定项 */
function removeTodo(id) {
    todos.value=todos.value.filter((t)=>t.id!==id)
}

// ------------------------ 隐藏已完成事项 ------------------------
const hideCompleted = ref(false);  // 是否隐藏

/** 隐藏已完成项 */
const filteredList = computed(() => {
    return hideCompleted.value
        ? todos.value.filter((t) => !t.done)
        : todos.value
})
</script>

<template>
    <div>
        <form @submit.prevent="addTodo">
            <input v-model="newTodo" required placeholder="Add a new Task" />
            <button type="submit">Add Todo</button>
        </form>
        <ul>
            <li v-for="todo in filteredList" :key="todo.id">
                <input type="checkbox" v-model="todo.done"/>
                <span :class="{done:todo.done}">{{ todo.text }}</span>
                <button @click="removeTodo(todo.id)">删除</button>
            </li>
        </ul>
        <button @click="hideCompleted = !hideCompleted">
            {{ hideCompleted ? 'Show All' : 'Hide completed'}}
        </button>
    </div>
</template>

<style>
.done{
    text-decoration:line-through;
}
</style>
