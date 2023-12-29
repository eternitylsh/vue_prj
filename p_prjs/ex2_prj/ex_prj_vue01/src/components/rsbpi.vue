<script setup>
    import { ref, reactive } from 'vue'

    const links = reactive({
        resbipi:         'https://ko.wikipedia.org/wiki/%EB%9D%BC%EC%A6%88%EB%B2%A0%EB%A6%AC_%ED%8C%8C%EC%9D%B4',
        resbipng:         new URL("../res/rspi4.png", import.meta.url).href,
        rspbg:           'https://techman-tooltip.tistory.com/117',
        rsbpi_community: 'https://www.raspberrypi.org/',
        com_science:     'https://ko.wikipedia.org/wiki/%EC%BB%B4%ED%93%A8%ED%84%B0_%EA%B3%BC%ED%95%99',
        rsbpi4:          'https://www.raspberrypi.com/products/raspberry-pi-4-model-b/specifications/'
    })

    const rspbackground = ref('간단하게 역사를 살펴보면 2006년 초기 컨셉으로 시작된 라즈베리 파이는 교사, 대학교, 컴퓨터 엔지니어 와 매니아들이 모여 재단을 만들면서 시작되었습니다.</br>\
            2012년 1월 29일에 출시된 제일 초기 버전인 "Raspberry Pi"는 정식 판매 이전에 이베이 경매를 통해서 등록해서 처음 만개의 보드를 판매하게 되는데, 이때 시리얼 넘버가 \'1\'인 보드는 3,500파운드(약 5,500,000원)까지 가격이 올라갔었다고 합니다.</br> \
            이때 라즈베리파이 보드의 정식적인 판매 가격은 사양에 따라 조금 다르지만 22 파운드(약 35,000원) 였습니다.</br>\
            그리고 2015년 "Raspberry Pi 2" 보드가 판매를 시작했고, 이때 조금 더 소형화 되고 가격이 저렴한 "Raspberry Pi Zero" 버전도 새로 나오게 되었습니다.</br>\
            이어지는 2016년에는 새로운 모델은 "Raspberry Pi 3" 버전이 출시된다 발표가 되었고, 국내에서는 이 시기부터 코딩이나 메이커 열풍이 불기 시작하면서 이전에 일부 메이커 또는 매니아 층에서만 유명했던 라즈베리파이가 많은 사람들에게 알려지는 계기가 되었습니다.</br>\
            그리고 작년, 2019년에 "Raspberry Pi 4" 버전의 보드가 출시되었습니다.</br>\
            1.5GHz quad-core 64-bit ARM Cortex-A72 CPU를 사용해 \'약 3배의 성능 향상\'이 있다고 한다. 메모리는 1GB, 2GB, 4GB 중 하나를 선택해서 구입을 할 수 있습니다.</br>\
            여기서 좀 대단하다고 느껴지는게 보드의 버전 업그레이드를 통해 성능이 향상되고 부품이 변경됨에도 불구하고 가격이 유지가 되고 있다는 점입니다.'
        )

    const spec_sum = reactive([
        { title: '프로세서', main: '쿼드 코어 ARM Cortex-A72 프로세서가 장착되어 이전 제품에 비해 성능이 크게 향상되었습니다.' },
        { title: 'RAM', main: '2GB부터 8GB까지 다양한 구성이 가능하며 LPDDR4 SDRAM을 사용하면 멀티태스킹 및 메모리 집약적인 애플리케이션이 가능합니다.' },
        { title: '연결성', main: ' 빠른 데이터 전송을 위한 듀얼 밴드 802.11ac 무선 LAN, 기가비트 이더넷, Bluetooth 5.0 및 USB 3.0 포트를 갖추고 있습니다.' },
        { title: '비디오 출력', main: '두 개의 4K 디스플레이를 동시에 구동할 수 있는 듀얼 마이크로 HDMI 포트를 지원합니다.' },
        { title: 'GPIO 핀', main: '다양한 센서, 모듈 및 주변 장치와 인터페이스하기 위해 40핀 GPIO 헤더를 유지합니다.' },
    ])

    const features = reactive([
        { title: 'USB-C 전원', main: '향상된 전원 공급을 위해 USB Type-C 전원 커넥터를 활용합니다.'},
        { title: '저장소', main: '저장용 MicroSD 카드 슬롯으로 저장 용량을 유연하게 선택할 수 있습니다.'},
        { title: '운영 체제(OS)', main: 'Raspbian(현재 Raspberry Pi OS라고 함)을 포함한 다양한 운영 체제와 호환되며 광범위한 애플리케이션을 지원합니다.'},
    ])

    const potential = reactive([
        { title: '교육 프로젝트', main: '학교 및 학습 환경에서 프로그래밍, 전자, 컴퓨터 과학을 가르치는 데 적합합니다.' },
        { title: '홈 자동화', main: '조명, 가전제품 및 기타 연결된 장치를 제어하는 ​​스마트 홈 프로젝트의 중앙 허브로 사용할 수 있습니다.' },
        { title: '미디어 센터', main: '4K 비디오 기능을 통해 Kodi 또는 Plex와 같은 애플리케이션을 실행하는 비용 효율적인 미디어 센터 역할을 할 수 있습니다.' },
        { title: '서버 애플리케이션', main: '웹 서버, 파일 서버 또는 NAS(Network Attached Storage) 실행과 같은 경량 서버 작업에 적합합니다.' },
        { title: 'DIY 프로젝트', main: '복고풍 게임 콘솔부터 기상 관측소 및 홈 보안 시스템에 이르기까지 다양한 DIY 프로젝트에 인기가 있습니다.' },
    ])

    const subtitleinfo = ref('')
</script>

<template>
    <div id="subtitleinfo">
        <h2><a v-bind:href="links.resbipi">라즈베리 파이</a></h2>
        <p ref="subtitleinfo">라즈베리 파이(영어: Raspberry Pi)는 영국 잉글랜드의 <span><a v-bind:href="links.rsbpi_community">라즈베리 파이 재단</a></span>이 학교와 개발도상국에서 기초 <span><a v-bind:href="links.com_science">컴퓨터 과학</a></span>의 교육을 증진시키기 위해 개발한 신용카드 크기의 싱글 보드 컴퓨터이다.</p>

        <h3><a v-bind:href="links.rspbg">등장 배경</a></h3>
        <p v-html="rspbackground"></p>
    </div>

    <div id="main">
        <h2>대표적 예로 <span><a v-bind:href="links.rsbpi4">라즈베리 파이4</a></span>에 관해서 대충요약으로 뚝딱.</h2>
        <img v-bind:src="links.resbipng" />
        <h3>재원</h3>
        <ul id="hw_specs">
            <li v-for="item in spec_sum">
                <span class="ititle">{{ item.title }}</span> : {{ item.main }}
            </li>
        </ul>

        <h3>특징</h3>
        <ul id="char">
            <li v-for="item in features">
                <span class="ititle">{{ item.title }}</span> : {{ item.main }}
            </li>
        </ul>

        <h3>잠재적 사용예</h3>
        <ol id="usecase">
            <li v-for="item in potential">
                <span class="ititle">{{ item.title }}</span> : {{ item.main }}
            </li>
        </ol>
    </div>

</template>

<style>
main h2{
    margin: 0.5rem;
}

main h3{
    margin: 0.25rem;
    font-weight: 600;
}

main .ititle {
    font-weight: 600;
}


</style>