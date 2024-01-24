<script setup>
    import { ref, reactive } from 'vue'
    import vcon from './RCSlider.vue'

    const isClicked = ref('false')

    const videoObj = ref({
        src: "../../assets/movie/Ice_Bear.mp4",
        preload: "metadata",
        muted: true,
        playsinline: true,

        currentTime: 0
    })

    const ntimeview = reactive({
        videoctime: 0,
        min: {
            h: 0,
            m: 0,
            s: 0,
            ss: 0,
            str: `${this.h}:${this.m}:${this.s}:${this.ss}`
        },
        max: {
            h: 0,
            m: 0,
            s: 0,
            ss: 0,
            str: `${this.h}:${this.m}:${this.s}:${this.ss}`
        },

        OnUpdate(__v) {
            // __v[0] : min
            // __v[1] : max
        },
    })

    const movieupdate = __v => {
    
        // 추후.. 원천 막을방법에 관해 고민을..
        // if( max_obj.value < min_obj.value ){ max_obj.value = min_obj.value; }
        // console.log( `${max_obj.value}, ${min_obj.value}`  )
        
        

        video_obj.currentTime = ( video_obj.duration / 100 ) * __v;
        movie_HTMLtimeline_update( video_obj.currentTime )

        if( isClicked ) {
            
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
</script>

<template>
    <div id="video_center">
        <div id="videoview" class="flex_center">
            <video class="video" ref="videoObj" @timeupdate="currentTime_ = $event.target.currentTime" />
        </div>
        <div id="ntime-view">
            <span>{{ ntimeview.min.str }}</span>
            <span>{{ ntimeview.max.str }}</span>
        </div>
        <vcon @svalues="__vs => movieupdate(__vs)" />
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

#ntime-view {
    margin: 0 auto;
    text-align: center;
}
#ntime-view span {
    font-size: 1.2rem;
    margin: 0.5rem;
}
</style>