<script setup>
    import { ref, computed } from 'vue'

    const props = defineProps({
        pdata: Array,
        pcolumns: Array,
        pfilterKey: String
    })

    const sortKey = ref('')

    const sortOrders = ref(
        props.pcolumns.reduce((o, key) => ((o[key] = 1), o), {})
    )

    const filteredData = computed(() => {
        let { data, filterKey } = props
        if (filterKey) {
            filterKey = filterKey.toLowerCase()
            data = data.filter((row) => {
            return Object.keys(row).some((key) => {
                return String(row[key]).toLowerCase().indexOf(filterKey) > -1
            })
            })
        }
        const key = sortKey.value
        if (key) {
            const order = sortOrders.value[key]
            data = data.slice().sort((a, b) => {
            a = a[key]
            b = b[key]
            return (a === b ? 0 : a > b ? 1 : -1) * order
            })
        }
        return data
    })
</script>

<template>

</template>