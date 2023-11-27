<template>
  <p>할 일 id: {{ todoId }}</p>
  <button @click="todoId++">다음 할 일 가져오기</button>
  <p v-if="!todoData">로딩...</p>
  <pre v-else>{{ todoData }}</pre>
  <hr>
  <nicec01 :msg="to_c1_str" @response="msg => c_nice = msg">부모가 보내는 : {{ c_nice2 }}</nicec01>
  <p>{{ c_nice }}</p>
</template>

<script setup>
import { ref, watch } from "vue";

import nicec01 from './child0/nice_c01.vue'

const todoId = ref(1);
const todoData = ref(null);

async function fetchData(__newid) {
  todoData.value = null;
  const res = await fetch(
    `https://jsonplaceholder.typicode.com/todos/${__newid}`
  );
  todoData.value = await res.json();
}

watch(todoId, (newId) => {
  fetchData(newId);
});

fetchData(todoId.value);

// ===================================

const to_c1_str = ref("wow~ completed~!")
const c_nice = ref('Can\'t read Nice_c01;;;')
const c_nice2 = ref('Wow! Nice c01!!!')

</script>
