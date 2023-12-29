<script setup>
    import { ref, reactive } from 'vue'

    const links = reactive({
        iiot          : 'https://ko.wikipedia.org/wiki/%EC%82%B0%EC%97%85_%EC%82%AC%EB%AC%BC%EC%9D%B8%ED%84%B0%EB%84%B7',
        iiotbg        : 'https://en.wikipedia.org/wiki/Industrial_internet_of_things',
        iiotpng       : new URL("../res/IIoT_Architecture.png", import.meta.url),
        dcs           : 'https://ko.wikipedia.org/wiki/%EB%B6%84%EC%82%B0_%EC%A0%9C%EC%96%B4_%EC%8B%9C%EC%8A%A4%ED%85%9C',
    })

    const iiotbg = ref('\
    IIoT의 역사는 1968년 Richard E. Morley 가 PLC( 프로그래머블 로직 컨트롤러 )를 발명하면서 시작됩니다. PLC는 General Motors 의 자동 변속기 제조 부문에서 사용되었습니다. 이러한 PLC를 사용하면 제조 체인의 개별 요소를 미세하게 제어할 수 있습니다. 1975년에 Honeywell 과 Yokogawa는 각각 세계 최초의 DCS인 TDC 2000과 CENTUM 시스템을 출시했습니다. 이러한 DCS는 중앙 제어실의 단일 장애 지점을 제거하여 전체 시스템에 제어를 분산함으로써 백업 중복의 추가 이점과 함께 공장 전체에서 유연한 프로세스 제어를 허용하는 다음 단계였습니다.\n\
    1980년 이더넷이 도입되면서 사람들은 1982년 초부터 스마트 장치 네트워크의 개념을 탐구하기 시작했습니다. 당시 카네기 멜론 대학교 의 수정된 콜라 기계가 최초의 인터넷 연결 기기가 되었고 목록을 보고할 수 있었습니다. 새로 넣은 음료가 차가운지 여부. 1994년 초에 Reza Raji가 IEEE Spectrum 의 개념 을 "소규모 데이터 패킷을 대규모 노드 세트로 이동하여 가전 제품의 모든 것을 통합하고 자동화하는 것"으로 설명했듯이 더 큰 산업 응용 프로그램이 구상되었습니다. 전체 공장에."\n\
    사물 인터넷의 개념은 1999년 MIT의 Auto-ID 센터 및 관련 시장 분석 간행물을 통해 처음 대중화되었습니다. RFID (무선 주파수 식별 )는 당시 사물 인터넷의 전제 조건으로 Kevin Ashton(원래 자동 ID 센터 창립자 중 한 명)에 의해 간주되었습니다. 일상생활의 모든 사물과 사람에게 식별자가 장착된다면 컴퓨터는 이를 관리하고 목록화할 수 있습니다. 사물의 태깅은 RFID 이외에도 근거리 무선 통신 , 바코드 , QR코드 , 디지털 워터마킹 등 의 기술을 통해 이루어질 수 있다.\n\
    현재의 IIoT 개념은 2002년 클라우드 기술이 출현하여 과거 추세를 조사하기 위해 데이터를 저장할 수 있게 되었고, 2006년 장치 간 안전한 원격 통신을 가능하게 하는 OPC 통합 아키텍처 프로토콜이 개발되면서 탄생했습니다. 사람의 개입이나 인터페이스가 필요 없는 프로그램 및 데이터 소스입니다.\n\
    산업용 사물 인터넷(사물에 아주 작은 식별 장치나 기계 판독 가능 식별자를 장착)을 구현한 첫 번째 결과 중 하나는 즉각적이고 끊임없는 재고 관리를 가능하게 하는 것입니다. IIoT 시스템 구현의 또 다른 이점은 시스템의 디지털 트윈을 생성할 수 있다는 것 입니다. 이 디지털 트윈을 사용하면 생산을 중단하거나 안전을 희생할 필요 없이 클라우드의 새로운 데이터를 실험할 수 있어 시스템을 더욱 최적화할 수 있습니다. 새로운 프로세스를 구현할 준비가 될 때까지 가상으로 개선할 수 있기 때문입니다. 디지털 트윈은 실제 시스템에 미치는 실제 영향을 걱정할 필요가 없는 신입 직원을 위한 교육장 역할도 할 수 있습니다.\n\
    ')

    // { title: '', main: ['', '',] },
    const spec_sum = reactive([
        { title: '연결성', main: [
            'IIoT에는 기계와 시스템 간의 원활한 통신을 가능하게 하는 상호 연결된 장치 및 센서의 네트워크가 포함됩니다.',
            '효율적인 데이터 교환을 위해 MQTT, CoAP, OPC UA 등의 통신 프로토콜이 사용되는 경우가 많습니다.',
        ] },
        { title: '센서 및 데이터 수집', main: [
            '다양한 센서를 활용하여 산업장비, 생산공정, 환경 등의 데이터를 실시간으로 수집합니다.',
            '센서는 온도, 압력, 습도, 진동 등과 같은 매개변수를 측정합니다.',
        ] },
        { title: '데이터 분석', main: [
            '고급 분석 도구를 사용하여 IIoT 장치에서 생성된 방대한 양의 데이터를 처리하고 분석합니다.',
            '예측 분석 및 기계 학습 알고리즘은 장비 오류를 예측하고 프로세스를 최적화하는 데 도움이 됩니다.',
        ] },
        { title: '클라우드 컴퓨팅', main: [
            '데이터 저장 및 처리를 위해 클라우드 플랫폼을 활용하여 확장성과 접근성을 제공하는 경우가 많습니다.',
            '클라우드 컴퓨팅을 통해 전 세계 어디에서나 실시간 모니터링, 데이터 저장, 분석이 가능합니다.',
        ] },
        { title: '보안', main: [
            '산업 프로세스의 중요한 특성으로 인해 사이버 보안에 중점을 둡니다.',
            '민감한 산업 데이터를 보호하기 위해 암호화, 액세스 제어, 인증 등의 보안 조치를 구현합니다.',
        ] },
    ])

    const Aexam = reactive([
        { title: '예측 유지 관리', main: [
            'IIoT를 사용하면 장비 상태를 실시간으로 모니터링하여 예측 유지 관리 전략을 구현할 수 있습니다.',
            '예측 유지보수는 가동 중단 시간을 줄이고 산업 기계의 수명을 연장하는 데 도움이 됩니다.',
        ] },
        { title: '스마트 제조', main: [
            '기계, 프로세스, 공급망이 상호 연결된 스마트 팩토리 구축을 촉진합니다.', 
            '제조 작업의 효율성, 품질 관리 및 전반적인 생산성을 향상시킵니다.',
        ] },
        { title: '공급망 최적화', main: [
            'IIoT는 생산부터 유통까지 전체 공급망에 대한 가시성을 제공합니다.', 
            '재고 관리를 최적화하고 리드 타임을 줄이며 전반적인 공급망 효율성을 향상시킵니다.',
        ] },
        { title: '에너지 관리', main: [
            '산업 시설의 에너지 소비를 모니터링하고 분석하여 개선 영역을 식별합니다.', 
            '에너지 효율적인 방식을 구현하고 운영 비용을 절감합니다.',
        ] },
        { title: '품질 관리', main: [
            '센서와 카메라를 통합하여 제조 공정 전반에 걸쳐 제품 품질을 모니터링하고 보장합니다.', 
            '실시간 조정이 가능해 불량 예방 및 제품 품질 향상이 가능합니다.',
        ] },
        { title: '자산 추적', main: [
            'RFID, GPS 등의 추적기술을 활용하여 자산의 위치와 상태를 실시간으로 모니터링합니다.', 
            '재고 관리를 개선하고 자산이 분실되거나 잘못 배치될 위험을 줄입니다.',
        ] },
    ])

    const advance = reactive([
        { title: '효율성 향상', main: [
            'IoT는 산업 프로세스를 최적화하여 효율성을 향상하고 폐기물을 줄이며 생산성을 향상시킵니다.'
        ] },
        { title: '비용 절감', main: [
            '예측적 유지보수와 효율적인 자원 활용으로 다운타임을 최소화하고 에너지 소비를 줄여 비용 절감에 기여합니다.', 
        ] },
        { title: '데이터 기반 의사결정', main: [
            'IIoT 장치에서 생성된 풍부한 실시간 데이터는 정보에 입각한 의사 결정 및 전략 계획을 수립하는 데 도움이 됩니다.', 
        ] },
        { title: '향상된 안전성', main: [
            'IIoT는 환경 조건 및 장비 성능에 대한 실시간 데이터를 제공하여 작업장 안전을 모니터링하고 관리하는 데 도움을 줍니다.', 
        ] },
        { title: '경쟁 우위', main: [
            'IIoT를 채택한 기업은 기술 혁신과 프로세스 최적화의 선두에 서서 경쟁 우위를 확보합니다.', 
        ] },
    ])
</script>

<template>
    <div id="subtitleinfo">
        <h2><a v-bind:href="links.iiot">IIOT(industrial internet of things) 산업 사물인터넷</a></h2>
        <p>
            산업 사물인터넷(industrial internet of things, IIoT)은 제조 및 에너지 관리를 포함한 컴퓨터의 산업 부문과 함께 네트워크로 상호 연결되어 있는 센서, 장비 등의 장치를 일컫는다.<br> 
            이러한 연결을 통해 데이터 수집, 교환, 분석, 그리고 생산과 효율성의 개선을 용이케 하는 것 및 그 밖의 경제적 이점을 실현시킬 수 있다. IIoT는 <span><a v-bind:href="links.dcs">분산 제어 시스템(DCS)</a></span>을 발전시킨 것으로, 프로세스 제어를 개선하기 위해 클라우드 컴퓨팅을 사용하여 높은 수준의 자동화를 가능케 한다.
        </p>
        <h3><a v-bind:href="links.iiotbg">등장 배경</a></h3>
        <p v-html="iiotbg"></p>
    </div>

    <div id="main">
        <div id="iiotimg">
            <img v-bind:src="links.iiotpng" />
        </div>
        <h2>간략하게 특징, 사용예, 이점등을 정리</h2>
        <ol id="iiot_f">
            <h3>특징</h3>
            <li v-for="item in Aexam">
                <span class="ititle">{{ item.title }}</span>
                <ul>
                    <li v-for="mi in item.main">{{ mi }}</li>
                </ul>
            </li>
        </ol>
        <ol id="iiot_ae">
            <h3>적용 예</h3>
            <li v-for="item in Aexam">
                <span class="ititle">{{ item.title }}</span>
                <ul>
                    <li v-for="mi in item.main">{{ mi }}</li>
                </ul>
            </li>
        </ol>
        <ol id="iiot_ad">
            <h3>이점</h3>
            <li v-for="item in spec_sum">
                <span class="ititle">{{ item.title }}</span>
                <ul>
                    <li v-for="mi in item.main">{{ mi }}</li>
                </ul>
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

main #subtitleinfo {
    margin-top: 2rem;
}

main #subtitleinfo #iiotimg {
    width: 100%;
    display: flex;
    justify-content: center;
}

main .ititle {
    font-weight: 600;
}
</style>