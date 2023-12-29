<script setup>
  import { ref } from 'vue'

  import rsbpi from './components/rsbpi.vue'
  import iiot from './components/iiot.vue'

  const title = ref('라즈베리 파이 및 IIOT 설명')
</script>

<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
  <main>
    <rsbpi></rsbpi>
    <iiot></iiot>
  </main>
</template>

<style>
header {
  margin-left: 2rem;
  line-height: 5.5rem;
}

header h1 {
  font-size: 2.5rem;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
</style>
