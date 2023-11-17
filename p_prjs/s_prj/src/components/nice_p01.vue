<template>
    <button>숫자 세기: {{ count }}</button>
  </template>

<script>
import { ref } from 'vue'

const count = ref(0)
</script>