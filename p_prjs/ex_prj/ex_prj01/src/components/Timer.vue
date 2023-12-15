<script setup>
    import { ref, onUnmounted } from 'vue'

    const vduration = ref(15)
    const elapsed = ref(0)


    let duration = ref(vduration.value * 1000)
    let lastTime = performance.now()
    let handle
    const update = () => {
        const time = performance.now()
        duration = ref(vduration.value * 1000)
        elapsed.value += Math.min(time - lastTime, duration.value - elapsed.value)
        lastTime = time
        handle = requestAnimationFrame(update)
    }

    update()
    onUnmounted(() => {
        cancelAnimationFrame(handle)
    })
</script>

<template>
    <label>Elapsed Time: 
        <progress :value="elapsed / duration"></progress>
    </label>
  
    <div>{{ (elapsed / 1000).toFixed(1) }}s</div>
  
    <div>
      Duration: 
      <input type="range" v-model="vduration" min="1" max="30" step="0.1">
      <input type="number" v-model="vduration" min="1" max="30" step="0.1">
      {{ (duration / 1000).toFixed(1) }}s
    </div>
  
    <button @click="elapsed = 0">Reset</button>
</template>

<style>
.elapsed-container {
  width: 300px;
}

.elapsed-bar {
  background-color: red;
  height: 10px;
}
</style>