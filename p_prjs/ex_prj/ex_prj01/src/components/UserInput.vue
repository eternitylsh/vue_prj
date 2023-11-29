<script setup>
    import { ref } from 'vue'

    const msg = ref('Hello World!')

    const reversemsg = () => {
        msg.value = msg.value.split('').reverse().join('')
    }

    const notify = () => {
        alert('navigation was prevented.')
    }
</script>

<template>
    <h1>{{ msg }}</h1>

    <button @click="reversemsg">Reverse Message</button>
    <button @click="msg += '!'">Append "!"</button>

    <a href="https://vuejs.org" @click.prevent="notify">
        A link with e.preventDefault()
    </a>
</template>

<style>
    button, a {
        display: block;
        margin-bottom: 1em;
    }
</style>