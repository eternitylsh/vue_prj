<script setup>
    import { ref, reactive } from 'vue'
    import vcon from './RCSlider.vue'

    const videoObj = ref(undefined)

    const ntimeview = reactive({
        inner: {
            h: 0,
            m: 0,
            s: 0,
            ss: 0
        },
        lenval: {
            val: 0,
            lenstr: `${0}:${0}:${0}:${0}`,
        },
        str: `${0}:${0}:${0}:${0}`,
        OnUpdate( __h, __m, __s, __ss ) {

            this.inner.h = __h
            this.inner.m = __m
            this.inner.s = __s
            this.inner.ss = __ss

            this.str = `${this.inner.h}:${this.inner.m}:${this.inner.s}:${this.inner.ss}`
        },

        OnMinMaxUpdate( __v ) {
            this.lenval.val = Math.abs( this.OnGetCurrentTime(__v[1]) - this.OnGetCurrentTime(__v[0]) ) // max - min
            this.lenval.lenstr = this.OnConvertTimeFormet(this.lenval.val)
        },

        OnConvertTimeFormet( __v ) {

            let _h = parseInt( __v / Math.pow(60, 2) )
            let _m = parseInt(__v / 60 )
            const _oris = __v % 60
            let _s = parseInt(_oris)
            let _ss = ( _oris % 1 ).toFixed(3).substr(2, 4)

            return `${_h}:${_m}:${_s}:${_ss}`
        },

        OnGetCurrentTime( __v ) {
            return ( videoObj.value.duration / 100 ) * __v
        },
    })

    const movieupdate = __v => {

        ntimeview.OnMinMaxUpdate( __v[0] )

        const video = videoObj.value

        // __v[0] = (min, max)
        // __v[1] = update value(최근 변경된 애만 저장.)
        video.currentTime = ntimeview.OnGetCurrentTime(__v[1].value);

        // console.log(video.currentTime)
        movie_HTMLtimeline_update( video.currentTime )
    }

    const movie_HTMLtimeline_update = __v => {

        let _h = parseInt( __v / Math.pow(60, 2) )
        let _m = parseInt(__v / 60 )
        const _oris = __v % 60
        let _s = parseInt(_oris)
        let _ss = ( _oris % 1 ).toFixed(3).substr(2, 4)

        ntimeview.OnUpdate( _h, _m, _s, _ss )
    }

</script>

<template>
    <div id="video_center">
        <div id="videoview" class="flex_center">
            <video class="video"
                src="../../assets/movie/Ice_Bear.mp4"
                preload="metadata"
                muted
                playsinline
                ref="videoObj" 
            />
        </div>
        <div id="ntimecview">
            <span>{{ ntimeview.str }} ( {{ ntimeview.lenval.lenstr }} )</span>
        </div>
        <vcon @svalues="movieupdate" />
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

#ntimecview {
    margin: 0 auto;
    text-align: center;
}
#ntimecview span {
    font-size: 1.2rem;
    margin: 0.5rem;
}
</style>