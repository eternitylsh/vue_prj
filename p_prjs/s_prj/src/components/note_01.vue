<template>
    <h4>1.응용 명령어 구조</h4>
    <p>{{ Lec.l01 }}</p>
    <p>{{ Lec.l02 }}</p>
    <div id="cal">
        <div class="cbox"><span>{{ Lec.cal.head }}</span></div>
        <span>+</span>
        <div class="cbox"><span>{{ Lec.cal.base }}</span></div>
        <span>+</span>
        <div class="cbox"><span>{{ Lec.cal.end }}</span></div>
    </div>
    <div>
        <ul v-html="Lec.head"></ul>
    </div>
    <div>
        <ul v-html="Lec.end"></ul>
    </div>
</template>

<script setup>   
    const Lec = {
        l01: "XGK PLC에서 접점과 코일을 이용할 경우 비트 데이터를 읽거나 쓸 수 있다. 그러나 XGK에서는 비트 데이터 이 외 니블(Nibble, 4 비트), 바이트(Byte, 8 비트), 워드(Word, 16비트), 더블 워드(Double Word, 32비트) 롱 워드(Long word, 64비트) 크기의 다양한 데이터를 취급할 수 있으며 이러한 데이터를 이용하여 연산하기 위해서는 응용 명령어를 사용해야 합니다.",
        l02: "XGK의 응용 명령어는 워드(16비트) 데이터를 처리하는 기본 명령어에 접두어와 접미어를 추가함으로써 기본 명령어의 기능을 추가 또는 제한하는 구조로 구성됩니다. 접두어와 접미어는 각각 2개까지 조합아여 사용이 가능합니다.",
        cal: {
            head: "접두어",
            base: "기본 명령어",
            end: "접미어",
        },
        head: `\
            <span>접두어: 기본 명령어 앞에 추가하여 기본 명령어의 기능을 보조하는 문자를 접두어라고 합니다. 하나의 기본 명령어에 최대 2개의 접두어를 사용 할 수 있습니다.</span>\
            <li>D: 더블 워드(Double Word, 32비트) 정수 데이터 연산. (예: DMOV, D=, DADD 등))</li>\
            <li>R: 32비트 실수 데이터 연산. (예: RMOV, R=, RDIV 등)</li>\
            <li>L: 64비트 실수 데이터 연산. (예: LMOV, L=, LADD 등)</li>\
            <li>G: 그룹 데이터 연산. (예: GMOV, G=, GADD 등)</li>\
            <li>B: 16 비트 데이터 내에서 비트 연산.(예: BMOV)</li>\
            <li>$: 문자열 데이터 연산. (예: $MOV, $ADD 등)</li>\
            <li>8: 8 비트 데이터 연산. (예: 8=, 8<, 8<> 등)</li>\
            <li>4: 4 비트 데이터 연산. (예: 4=, 4<> 등)</li>\
        `,
        end: `\
            <span>접미어: 기본 명령어 뒤에 추가하여 기본 명령어의 기능을 보조하는 문자를 접미어라고 합니다. 하나의 기본 명령어에 최대 2개의 접미어를 사용 할 수 있습니다.</span>\
            <li>U: 기본 명령어가 부호 있는 십진 정수 데이터를 연산할 때 부호 없는 십진 정수 데이터 연산. (예: ADDU 등)</li>\
            <li>P: 레벨 연산 응용 명령어의 상승 에지 연산.(예: MOVP, DIVP 등)</li>\
            <li>B: 기본 명령어가 십진 정수 데이터 연산할 때 BCD 데이터 연산. (예: ADDB, MULB 등)</li>\
            <li>8: 8 비트 데이터 연산. (예: MOV8, BCD8 등)</li>\
            <li>4: 4 비트 데이터 연산. (예: MOV4, BCD4 등)</li>\
            <li>3: 2개의 데이터 연산 기본 명령어에서 3개의 데이터 처리.(예: =3, <>3 등)</li>\
        `
        // head: {
        //     obj: document.querySelector('#head ul'),
        //     title: "접두어: 기본 명령어 앞에 추가하여 기본 명령어의 기능을 보조하는 문자를 접두어라고 합니다. 하나의 기본 명령어에 최대 2개의 접두어를 사용 할 수 있습니다.",
        //     infos: [
        //         "D: 더블 워드(Double Word, 32비트) 정수 데이터 연산. (예: DMOV, D=, DADD 등))",
        //         "R: 32비트 실수 데이터 연산. (예: RMOV, R=, RDIV 등)",
        //         "L: 64비트 실수 데이터 연산. (예: LMOV, L=, LADD 등)",
        //         "G: 그룹 데이터 연산. (예: GMOV, G=, GADD 등)",
        //         "B: 16 비트 데이터 내에서 비트 연산.(예: BMOV)",
        //         "$: 문자열 데이터 연산. (예: $MOV, $ADD 등)",
        //         "8: 8 비트 데이터 연산. (예: 8=, 8<, 8<> 등)",
        //         "4: 4 비트 데이터 연산. (예: 4=, 4<> 등)",
        //     ],
        // },
        // end: {
        //     obj: document.querySelector('#end ul'),
        //     title: "접미어: 기본 명령어 뒤에 추가하여 기본 명령어의 기능을 보조하는 문자를 접미어라고 합니다. 하나의 기본 명령어에 최대 2개의 접미어를 사용 할 수 있습니다.",
        //     infos: [
        //         "U: 기본 명령어가 부호 있는 십진 정수 데이터를 연산할 때 부호 없는 십진 정수 데이터 연산. (예: ADDU 등)",
        //         "P: 레벨 연산 응용 명령어의 상승 에지 연산.(예: MOVP, DIVP 등)",
        //         "B: 기본 명령어가 십진 정수 데이터 연산할 때 BCD 데이터 연산. (예: ADDB, MULB 등)",
        //         "8: 8 비트 데이터 연산. (예: MOV8, BCD8 등)",
        //         "4: 4 비트 데이터 연산. (예: MOV4, BCD4 등)",
        //         "3: 2개의 데이터 연산 기본 명령어에서 3개의 데이터 처리.(예: =3, <>3 등)",
        //     ],
        // },
    }    
</script>

<style>
    #cal .cbox {
        border: 1px solid black;
        width: 8rem;
        height: 2.5rem;

        display: inline-block;
        margin: 1rem;

        text-align: center;
        line-height: 2.5rem;
    }

    #cal .cbox ul li {
        padding-left: 2rem;
    }
</style>