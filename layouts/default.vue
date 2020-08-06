<template>
  <div class="app-container" :class="{ dark: isDarkMode }">
    <div class="container">
      <Header @changed="toggleDarkMode" />
      <Nuxt />
      <Footer />
    </div>
  </div>
</template>
<script>
import Header from '../components/Header'
import Footer from '../components/Footer'

export default {
  components: { Header, Footer },
  data() {
    return {
      isDarkMode: false,
    }
  },
  methods: {
    toggleDarkMode() {
      return (this.isDarkMode = !this.isDarkMode)
    },
  },
}
</script>

<style lang="scss">
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

// h6,
// h5,
// h4,
// h3,
// h2,
// h1,
// p {
// }

.app-container {
  &.dark {
    color: white;
    background: black;
  }
}

.container {
  min-height: 100vh;
  max-width: 900px;
  margin: 0 auto;
  position: relative;
}
</style>
