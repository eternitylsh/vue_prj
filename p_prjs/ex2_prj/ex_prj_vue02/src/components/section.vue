<script setup>
    import { ref, reactive } from 'vue'
    import dzone from './section/Dropzone.vue'
    // import vm from './section/ViewMovie.vue'

    const props = defineProps({
        msg: String
    })

    const videoview = ref(false)
</script>

<template>
    <span>{{ msg }}</span><br>
    <dzone/>
    <!-- <vm/> -->
</template>