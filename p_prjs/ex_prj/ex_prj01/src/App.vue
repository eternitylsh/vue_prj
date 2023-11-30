<script setup>
// import userinput from './components/UserInput.vue'
// import bindcomp from './components/bind01.vue'
// import condloop from './components/condloop.vue'
import fbind from './components/f_bind02.vue'

const title = "다양한 예시모음..."

</script>

<template>
  <header>
    <h1>{{ title }}</h1>
  </header>

  <main>
    <!-- <userinput>
      <h2>'HelloWorld'</h2>
    </userinput> -->
    <!-- <bindcomp></bindcomp>
    <condloop></condloop> -->
    <fbind></fbind>
  </main>
</template>

<style>
</style>