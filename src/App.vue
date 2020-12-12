<template>
  <div id="app">
    <Header/>
    <Searchbar/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Searchbar from './components/Searchbar.vue'

export default {
  name: 'App',
  components: {
    Header,
    Searchbar
  }
}
</script>

<style>
html {
  box-sizing: border-box;
  font-size: 1em;
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
