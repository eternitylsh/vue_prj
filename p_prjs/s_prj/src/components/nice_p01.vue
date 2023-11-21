<template>
  <!-- <button @click="fn">숫자 세기: {{ count }}</button> -->

  <!-- <hr> -->

  <!-- <input :value="text" @input="onInput" placeholder="여기에 입력하기"><br>
    {{ text }} -->

  <!-- <hr> -->

  <!-- <form @submit.prevent="addTodo">
        <input v-model="newTodo">
        <button>할 일 추가</button>
    </form>
    <ul>
        <li v-for="todo in filteredTodos" :key="todo.id">
            <input type="checkbox" v-model="todo.done">
            <span :class="{ done: todo.done }">{{ todo.text }}</span>
            <button @click="RemoveTodo(todo)">X</button>
        </li>
    </ul>
    <button @click="hideCompleted = !hideCompleted">
        {{ hideCompleted ? 'Show all' : 'Hide completed' }}
    </button> -->

  <!-- <hr> -->

  <p ref="p">안녕</p>
</template>

<script setup>
// import { ref, computed } from 'vue'
// import { text } from 'body-parser';
import { ref, onMounted } from "vue";

// const count = ref(0)

// const fn = () => {
//     count.value++;
// }

// ==================================

// const text = ref('')

// const onInput = e => {
//     text.value = e.target.value
// }

// ==================================

// 고유id 부여..
// let id = 0

// const newTodo = ref('')
// const hideCompleted = ref(false)
// const todos = ref([
//         { id: id++, text: 'HTML 배우기', done: true },
//         { id: id++, text: 'Javascript 배우기', done: true },
//         { id: id++, text: 'Vue 배우기', done: false },
//     ])

// const filteredTodos = computed(() => {
//     // `todos.value` 및 `hideCompleted.value`를
//     // 기반으로 필터링된 할 일을 반환.
//     return hideCompleted.value
// ? todos.value.filter((t) => !t.done)
// : todos.value
// })

// const addTodo = () => {
//     todos.value.push({id: id++, text: newTodo.value, done: false})
//     newTodo.value = ''
// }

// const RemoveTodo = todo => {
//     todos.value = todos.value.filter(val => val.id !== todo.id)
// }

// ==================================

const p = ref(null);

onMounted(() => {
  p.value.textContent = "안녕하세요.";
  p.value.style.color = "aqua";
});
</script>

<style>
/* .done {
  text-decoration: line-through;
} */

/* ================================== */
</style>
