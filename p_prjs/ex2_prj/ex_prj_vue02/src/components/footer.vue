<script setup>
    const props = defineProps({
        msg: String
    })
</script>

<template>
    <span>{{ msg }}</span>
</template>

<style>
footer span {
    color : white;
}
</style>