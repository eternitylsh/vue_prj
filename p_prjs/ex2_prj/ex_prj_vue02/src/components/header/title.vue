<script setup>
    const props = defineProps({
        msg: String
    })
</script>

<template>
    <h1>{{ msg }}</h1>
</template>

<style>
header h1 {
    color : #DCF2F1;

    font-family: 'Hi Melody', cursive;
    font-weight: 600;
    line-height: 8rem;
    font-size : 3rem;
}
</style>