<script setup>
  import { ref, reactive } from 'vue';

  import Header from './components/header.vue'
  import Nav from './components/nav.vue'
  import Section from './components/section.vue'
  import Aside from './components/aside.vue'
  import Footer from './components/footer.vue'

  const sign = reactive({
    title: "header",
    nav: "nav",
    section: "section",
    aside: "aside",
    footer: "footer"
  })
</script>

<template>
  <header>
    <Header :msg="sign.title"/>
  </header>
  <nav>
    <Nav :msg="sign.nav" />
  </nav>
  <main>
    <section>
      <Section :msg="sign.section"/>
    </section>
    <aside>
      <Aside :msg="sign.aside" />
    </aside>
  </main>
  <footer>
    <Footer :msg="sign.footer" />
  </footer>
</template>

<style scoped>

main {
  width: 100%;
  height: 68%;

  display: flex;
  flex-direction: row;
}

main section {
  width: 75%;
  background-color:#7FC7D9;
}

main aside {
  width: 25%;
  background-color: #365486;
}

footer {
  width: 100%;
  height: 12%;

  background-color: #0F1035;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    /* place-items: center; */
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

.pull-left {
  float: left;
}
</style>
