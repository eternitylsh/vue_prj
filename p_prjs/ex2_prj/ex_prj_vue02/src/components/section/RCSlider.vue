<script setup>
    import { reactive } from 'vue'
    import Slider from '@vueform/slider'

    const value = reactive([25, 75])

    const emit = defineEmits(['svalues'])
    emit('svalues', value)
</script>

<template>
    <div id="multi-slider">
     <Slider v-model="value" class="slider-blue"
        :min="0"
        :max="100"
        :step="0.1"
        :tooltips="false"
        :classes="{
            horizontal: 'slider-horizontal h-2.5',
        }"
     />
    </div>
</template>

<style src="@vueform/slider/themes/default.css"></style>
<style>
#multi-slider {
    margin: 1.2rem auto;
    width: 50%;
}

.slider-blue {
  --slider-connect-bg: #3B82F6;
  --slider-tooltip-bg: #3B82F6;
  --slider-handle-ring-color: #3B82F630;
}
</style>