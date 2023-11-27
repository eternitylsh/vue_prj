<template>
    <div>{{ hello }} {{ props.msg || '없는 값..' }}</div>
    <slot>Can't Accept my parents...</slot>
</template>

<script setup>
    import { ref, defineProps, defineEmits } from "vue";

    const hello = ref('wow~')
    const emit = defineEmits('[response]')

    emit('response', '자식 컴포넌트로 부터 데이터 받기~')

    const props = defineProps({
        msg: String,
    })

</script>