<script setup>
  import { reactive } from 'vue';

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
    {{ sign.title }}
  </header>
  <nav>
    {{ sign.nav }}
  </nav>
  <main>
    <section>{{ sign.section }}</section>
    <aside>{{ sign.aside }}</aside>
  </main>
  <footer>{{ sign.footer }}</footer>
</template>

<style scoped>
header {
  width: 100%;
  height: 12%;

  background-color: #365486;
  color : white;
}

nav {
  width: 100%;
  height: 8%;

  background-color:#DCF2F1;
}

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

  color : white;
}

footer {
  width: 100%;
  height: 12%;

  background-color: #0F1035;

  color : white;
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
</style>
