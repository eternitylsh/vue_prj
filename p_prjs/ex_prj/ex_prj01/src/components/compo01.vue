<script setup>
    import { ref } from 'vue'
    import TItem from './childv01/ctodo.vue'

    const g_List = ref([
        { id: 0, text: 'Vegetables' },
        { id: 1, text: 'Cheese' },
        { id: 2, text: 'Whatever else humans are supposed to eat' },
        { id: 3, text: 'Same vegetables..' }
    ])
</script>

<template>
    <ol>
        <TItem
            v-for="item in g_List"
            :todo="item"
            :key="item.id"
        ></TItem>    
    </ol>
</template>