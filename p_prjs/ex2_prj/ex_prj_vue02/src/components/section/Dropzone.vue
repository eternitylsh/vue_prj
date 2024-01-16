<script setup>
    import { ref } from 'vue'
    import { useDropzone } from "vue3-dropzone";
    
    function onDrop(acceptFiles, rejectReasons) {
        console.log(acceptFiles);
        console.log(rejectReasons);
    }
    
    const { getRootProps, getInputProps } = useDropzone({ onDrop });
    const isDragActive = ref(false)
</script>

<template>
    <div>
        <div class="upField cm-ac mt10 mb10" v-bind="getRootProps()">
            <input v-bind="getInputProps()" type="file" />
            <p v-if="isDragActive">Drop the files here ...</p>
            <p v-else>Drag 'n' drop some files here, or click to select files</p>
        </div>
    <button @click="open">open</button>
  </div>
</template>

<style>

</style>