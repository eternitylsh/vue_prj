<script setup>
    import Title from './header/title.vue'
    
    const props = defineProps({
        msg: String
    })

    const hobjs = {
        Title: "Vue의 구성에 관해서.",
    }
</script>

<template>
    <span>{{ msg }}</span>
    <Title :msg="hobjs.Title" />
</template>

<style>
header span {
    color : white;
}
</style>