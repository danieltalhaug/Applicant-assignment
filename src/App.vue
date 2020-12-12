<template>
  <div id="app">
    <Header/>
  </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style>
html {
  box-sizing: border-box;
  font-size: 16px;
  font-family: Roboto;
}

*, *:before, *:after {
  box-sizing: inherit;
}
#app {
  margin: 0 auto;
  max-width: 1200px;
}

body, h1, h2, h3, h4, h5, h6, p, ol, ul {
  margin: 0;
  padding: 0;
  font-weight: normal;
}

ol, ul {
  list-style: none;
}

img {
  max-width: 100%;
  height: auto;
}
</style>
