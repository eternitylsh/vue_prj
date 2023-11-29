<script setup>
import userinput from './components/UserInput.vue'

const title = "다양한 예시모음..."

</script>

<template>
  <header>
    <h1>{{ title }}</h1>
  </header>

  <main>
    <userinput>
      <h2>'HelloWorld'</h2>
    </userinput>
  </main>
</template>

<style>

</style>