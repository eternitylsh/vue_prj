<script setup>
    import DGrid from './childv01/grid.vue'
    import { ref } from 'vue'

    const shQuery = ref('')
    const gridColumns = ['name', 'power']
    const gridData = [
    { name: 'Chuck Norris', power: Infinity },
    { name: 'Bruce Lee', power: 9000 },
    { name: 'Jackie Chan', power: 7000 },
    { name: 'Jet Li', power: 8000 }
    ]
</script>

<template>
    <form id="search">
        Search <input name="query" v-model="shQuery">
    </form>
  <DemoGrid
    :data="gridData"
    :columns="gridColumns"
    :filter-key="searchQuery">
  </DemoGrid>
</template>