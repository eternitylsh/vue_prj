<script setup>
    import { reactive } from 'vue'
    import Slider from '@vueform/slider'

    const value = reactive([25, 75])
    console.log(value.target)
</script>

<template>
    <div id="ntime-view">
        <span>00:00:00:000</span>
    </div>
    <div id="multi-slider">
     <Slider v-model="value"
        :min="0"
        :max="100"
        :step="0.1"
        
     />
    </div>
</template>

<style src="@vueform/slider/themes/default.css"></style>
<style>
#ntime-view {
    margin: 0 auto;
    text-align: center;
}
#ntime-view span {
    font-size: 1.2rem;
}

#multi-slider {
    margin-top: 2.6rem;
    width: 50%;
}
</style>