<script setup>
    import { reactive } from 'vue'

    const COLS = 5
    const ROWS = 20

    export const cells = reactive(
        Array.from(Array(COLS).keys()).map((i) =>
            Array.from(Array(ROWS).keys()).map((i) => '')
        )
    )

    
</script>

<template>

</template>