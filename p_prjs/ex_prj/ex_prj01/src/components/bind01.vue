<script setup>
    import { ref } from 'vue'

    const p = 'test..'

    const msg = ref('Hello World!')
    const isred = ref(true)
    const color = ref('green')

    const toggle_red = () => {
        isred.value = !isred.value
    }

    const tog_color = () => {
        console.log( color.value )
        color.value = ( 'green' === color.value ) ? 'blue' : 'green'
    }
</script>

<template>
    <p>
        <span :title="msg">
            Hover your mouse over me for a few seconds to see my dynamically bound title!
        </span>
    </p>

    <p :class="{ red: isred }" @click="toggle_red">
        This should be red... but click me to toggle it.
    </p>

    <p :style="{ color }" @click="tog_color">
        This should be green, and should toggle between green and blue on click.
    </p>
</template>

<style>
.red {
  color: red;
}
</style>