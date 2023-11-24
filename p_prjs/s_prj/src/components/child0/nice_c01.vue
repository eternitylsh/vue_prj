<template>
    <div>{{ hello }} {{ props.msg || '없는 값..' }}</div>
</template>

<script setup>
    import { ref, defineProps } from "vue";

    const hello = ref('wow~')

    const props = defineProps({
        msg: String,
    })

</script>