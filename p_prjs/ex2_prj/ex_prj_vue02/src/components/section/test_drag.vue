<script setup>
    import { reactive } from 'vue';
    const target = reactive({
        cstyle: {
            top: '0px',
            left: '0px'
        },

        click: false
    })

    const ObjMove = e => {

        if( target.click ) {

            const newstyle = {
                top: `${e.screenY}px`,
                left: `${e.screenX}px`
            }

            target.cstyle = newstyle
            console.log(true)
        }

        
        console.log(e.screenX, e.screenY)
    }


    // 추후 사용법에 대해 알아보기.
    // watch(() => target.cstyle, () => {
    //     clearError();

    //     if( target.click ) {

    //         const newstyle = {
    //             top: `${e.screenY}px`,
    //             left: `${e.screenX}px`
    //         }

    //         target.cstyle = newstyle
    //         console.log(true)
    //     }
    // });
</script>

<template>
    <div class="actarea">
    
        <div class="target" 
            v-on:mousedown="e => target.click = true"  
            v-on:mouseup="e => target.click = false" 
            v-bind:style="target.cstyle"
        >
        </div>
    
    </div>
</template>

<style>
.target {
    position: absolute;

    width: 100px;
    height: 100px;

    border-radius: 50%;

    background-color: beige;
}
</style>