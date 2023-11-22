<template>
    <div>
        <h1>{{ title }}</h1>
        <h3>{{ subinfo }}</h3>
    </div>
    <div>
        <img :src="obj.link1">
        <p>{{ obj.l1_sub }}</p>
        <img :src="obj.link2">
        <p>{{ obj.l2_sub }}</p>
        <p>{{ obj.l2_q }}</p>
        <img :src="obj.link3">
        <p>{{ obj.l3_sub }}</p>
        <img :src="obj.link4">
        <p>{{ obj.l4_sub }}</p>
    </div>
</template>

<script setup>
    import { ref, reactive } from 'vue'
    const title = ref('PLC에서의 사칙연산.. 온도계 구하기에 관해서..')
    const subinfo = ref('PLC를 통한 LD언어를 통해 프로그래밍에서 늘 쓰이는 사칙연산이 LD에서 어떻게 특히 온도계 방식으로 구현될 것인지 확인해보자.')
    const obj = reactive({
        link1: require(`../assets/note2/main.png`),
        l1_sub: '사칙연산, 에러플래그 연결, 실수연산 등 기본적인 회로구성을 보여준다.',
        link2: require(`../assets/note2/sub01_0.png`),
        l2_sub: '위 회로를 바탕으로 온도계 회로를 구성하며 문제를 구성',
        l2_q: '문제또한 구성을 진행. 1. 12mA > 몇도?, 2. 88도 면 ??mA… 이러한 두 문제를 푸는 목적으로 구성.',
        link3: require(`../assets/note2/sub01_1.png`),
        l3_sub: '첫번째 문제 해답의 회로구성',
        link4: require(`../assets/note2/sub01_2.png`),
        l4_sub: '두번째 문제 해답의 회로구성',
    })
</script>