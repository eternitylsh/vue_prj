<script setup>
    import { ref } from 'vue'
    // import vcon from './RCSlider.vue'
    import testdrag from './test_drag.vue'

    const isClicked = ref('false')

    const movieupdate = __v => {
    
        // 추후.. 원천 막을방법에 관해 고민을..
        if( max_obj.value < min_obj.value ){ max_obj.value = min_obj.value; }
        // console.log( `${max_obj.value}, ${min_obj.value}`  )
        
        if( isCLicked ) {
            video_obj.currentTime = ( video_obj.duration / 100 ) * __v;
            movie_HTMLtimeline_update( video_obj.currentTime )
        }
    }

    const movie_HTMLtimeline_update = __v => {
        let _h = parseInt( __v / Math.pow(60, 2) );
        let _m = parseInt(__v / 60 );
        let _s = parseInt(__v % 60);
        let _ss = Number( ((__v % 60).toFixed(3) ) );
        // tofixed(3) 의 숫자 3은 UI상 표시되는 second이하 수치.
        ntime_view.innerHTML = `${_h}:${_m}:${_s}:${_ss}`;
    }

    const OnMdown = () => {
        isClicked.value = true;
    }

    const onMup = () => {
        isCLicked.value = false
    }
</script>

<template>
    <div id="video_center">
        <div id="videoview" class="flex_center">
            <video class="video" src="../../assets/movie/Ice_Bear.mp4" frameborder="0" preload="metadata" muted playsinline />
        </div>
        <!-- <vcon/> -->
        <testdrag />
    </div>
</template>

<style>
#video_center {
    display: block;
}

#videoview {
    width: 100%;
    text-align: center;
}

#videoview video {
    width: 50%;
    height: 50%;
    margin: 0 auto;
}

#videopannel-control {
    margin-top: 30px;
}
</style>