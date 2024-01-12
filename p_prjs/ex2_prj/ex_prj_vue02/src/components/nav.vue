<script setup>
    import {ref, reactive} from 'vue'
    const props = defineProps({
        msg: String
    })

    const menus = reactive({
        objs: [
            {   
                title:'구성1', 
                view: ref(false),
                items: reactive([
                    { name: '링크1', link: '#' }, 
                    { name: '링크2', link: '#' },
                    { name: '링크3', link: '#' },
                ])
            },
            {   
                title:'구성2', 
                view: ref(false),
                items: reactive([
                    { name: '링크1', link: '#' }, 
                    { name: '링크2', link: '#' },
                    { name: '링크3', link: '#' },
                ])
            },
            {   
                title:'구성3', 
                view: ref(false),
                items: reactive([
                    { name: '링크1', link: '#' }, 
                    { name: '링크2', link: '#' },
                    { name: '링크3', link: '#' },
                ])
            },
        ],
    })

    const mover = function(idx) {
        menus.objs[idx].view = true;
    }

    const mleave = function(idx) { 
        menus.objs[idx].view = false;
    }
</script>

<template>
    <!-- <span>{{ msg }}</span> -->
    <div class="pull-left">
        <ul class="outer-menu">
            <li class="outer-menu-item" v-on:mouseover="mover(idx)" v-on:mouseleave="mleave(idx)" v-for="(item, idx) in menus.objs">
                <span class="menu-title" >{{ item.title }}</span>
                <ul class="inner-menu" v-if="menus.objs[idx].view">
                    <li class="inner-menu-item" v-for="iitem in item.items">
                        <a v-bind:href="iitem.link"> {{ iitem.name }} </a>
                    </li>
                </ul>
            </li>
        </ul>
    </div>
</template>

<style>
nav {
    width: 100%;
    height: 8%;

    background-color:#DCF2F1;

    font-size: 1rem;

    border-top: 1px solid #0F1035;
    border-bottom: 1px solid #0F1035;
}

nav>span {
    position: relative;
}

nav li {
    list-style: none;
}

.outer-menu {
    margin: 0 1.2rem;
}

.outer-menu-item {
    list-style: none;
    font-size: 1rem;
    line-height: 3.75rem;

    float: left;
    position: relative;
}

.menu-title {
    display: block;
    text-align: center;
    padding: 0.25rem 1.2rem;

    font-size: 1.2rem;
}

.inner-menu {
    display: block;
    position: absolute;
    top: 2.5rem;
    left: 0;
    padding-left: 0;
    width: 100%;

    background: #DCF2F1;
    box-shadow: 0 2px 6px #0F1035;
    z-index: 100;
    text-align: center;
}

.inner-menu-item > a {
    display: block;
    padding: 5px 10px;
    color: #0F1035;

    line-height: 1.5rem;
}


</style>