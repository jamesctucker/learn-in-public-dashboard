<template>
  <header>
    <nav class="nav p-8 flex justify-between">
      <div class="brand mr-8">
        <n-link to="/">
          <h1>JT</h1>
        </n-link>
      </div>
      <div class="nav-links flex">
        <div class="nav-link mr-4"><n-link to="/about">About</n-link></div>
        <div class="nav-link mr-4">
          <n-link to="/learning">Learning</n-link>
        </div>
        <div class="nav-link mr-4"><n-link to="/blog">Blog</n-link></div>
        <div class="dark-mode-toggle">
          <button @click="toggleDarkTheme">
            <moon-icon
              v-if="!isDarkMode"
              size="25"
              class="custom-class"
            ></moon-icon>
            <sun-icon v-else size="25" class="custom-class"></sun-icon>
          </button>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
import { SunIcon, MoonIcon } from 'vue-feather-icons'

export default {
  name: 'Header',
  components: { MoonIcon, SunIcon },
  data() {
    return {
      isDarkMode: false,
    }
  },
  methods: {
    toggleDarkTheme() {
      this.isDarkMode = !this.isDarkMode
      console.log('dark')
      this.$emit('changed')
    },
  },
}
</script>
