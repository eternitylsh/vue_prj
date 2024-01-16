<script setup>
    import { ref, reactive } from 'vue'

    // 해당 스크립트 vue화 진행중;; 0116

//     const inputLeft = document.getElementById("input-left");
// const inputRight = document.getElementById("input-right");

// const thumbLeft = document.querySelector(".slider > .thumb.left");
// const thumbRight = document.querySelector(".slider > .thumb.right");
// const range = document.querySelector(".slider > .range");

    const rcs = reactive({
        main: {
            min: ref(),
            max: ref(),
        },
        thumb: {
            left: {
                left: '25%',
                transform: 'translate(-15px, -10px)',
            },
            right: {
                right: '25%',
                transform: 'translate(15px, -10px)',
            }
        },

        range: {
            position: 'absolute',
            zIndex: '2',
            left: '25%',
            right: '25%',
            top: '0',
            bottom: '0',
            borderRadius: '5px',
            backgroundColor: '#6200ee'
        }
    })

    const [min, max] = [ref(0), ref(0)]

    const setLeftValue = () => {
        //const _this = inputLeft;
        //const [min, max] = [parseInt(_this.min), parseInt(_this.max)];
        // 교차되지 않게, 1을 빼준 건 완전히 겹치기보다는 어느 정도 간격을 남겨두기 위해.
        rcs.min.value = Math.min(parseInt(rcs.main.min), parseInt(rcs.main.max) - 1);
        // input, thumb 같이 움직이도록
        const percent = ((rcs.main.min - rcs.main.min) / (rcs.main.max - rcs.main.min)) * 100;
        rcs.thumb.left = percent + "%";
        rcs.range.left = percent + "%";
    };

    const setRightValue = () => {
        // const _this = inputRight;
        // const [min, max] = [parseInt(_this.min), parseInt(_this.max)];
        // // 교차되지 않게, 1을 더해준 건 완전히 겹치기보다는 어느 정도 간격을 남겨두기 위해.
        // _this.value = Math.max(parseInt(_this.value), parseInt(inputLeft.value) + 1);
        // // input, thumb 같이 움직이도록
        // const percent = ((_this.value - min) / (max - min)) * 100;
        // thumbRight.style.right = 100 - percent + "%";
        // range.style.right = 100 - percent + "%";
        rcs.min.value = Math.max(parseInt(rcs.main.min), parseInt(rcs.main.max) + 1);
        const percent = ((rcs.main.min - rcs.main.min) / (rcs.main.max - rcs.main.min)) * 100;
        rcs.thumb.right = 100 - percent + "%";
        rcs.range.right = 100 - percent + "%";
    };

    inputLeft.addEventListener("input", setLeftValue);
    inputRight.addEventListener("input", setRightValue);

</script>

<template>
    <div id="videocontrol" class="flex_center">
        <p id="ntime_view">00:00:00:000</p>
        <!-- <p>min</p>
        <input type="range" min="0" max="100" step="0.1" class="form-range" id="min_input">
        <p>max</p>
        <input type="range" min="0" max="100" step="0.1" class="form-range" id="max_input"> -->

        <div class="middle">
            <div class="multi-range-slider">
                <input type="range" id="input-left" v-bind:value="rcs.main.min" min="0" max="100" step="0.1" value="25" />
                <input type="range" id="input-right" v-bind:value="rcs.main.max" min="0" max="100" step="0.1" value="75" />

                <div class="slider">
                    <div class="track"></div>
                    <div class="range" v-bind:style="rcs.range"></div>
                    <div class="thumb left" v-bind:style="rcs.thumb.left"></div>
                    <div class="thumb right" v-bind:style="rcs.thumb.right"></div>
                </div>
            </div>
        </div>
    </div>
    
</template>

<style>
#videocontrol {
    width: 100%;
    flex-direction: column;
}

#videocontrol p {
    text-align: center;
    margin: 0;
}

/* #videocontrol input{
    display: block;
    width: 50%;
    margin: 0 auto;
} */

.middle {
  position: relative;
  width: 50%;
  max-width: 500px;
}

.slider {
  position: relative;
  z-index: 1;
  height: 10px;
  margin: 0 15px;
}
.slider > .track {
  position: absolute;
  z-index: 1;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  border-radius: 5px;
  background-color: #c6aee7;
}
.slider > .range {
  position: absolute;
  z-index: 2;
  left: 25%;
  right: 25%;
  top: 0;
  bottom: 0;
  border-radius: 5px;
  background-color: #6200ee;
}
.slider > .thumb {
  position: absolute;
  z-index: 3;
  width: 30px;
  height: 30px;
  background-color: #6200ee;
  border-radius: 50%;
}

input[type="range"] {
  position: absolute;
  /* opacity로 가린 것을 이벤트도 비활성화하기 위해 */
  pointer-events: none;
  -webkit-appearance: none;
  z-index: 2;
  height: 10px;
  width: 100%;
  opacity: 0;
}
input[type="range"]::-webkit-slider-thumb {
  /* 겹쳐진 두 thumb를 모두 활성화 */
  pointer-events: all;
  width: 30px;
  height: 30px;
  border-radius: 0;
  border: 0 none;
  background-color: red;
  cursor: pointer;

  /* appearance를 해야 위의 스타일들을 볼 수 있음 */
  -webkit-appearance: none;
}
</style>