<template>
  <main>
    <h1>Vue Popups</h1>
    <button>Open Popup</button>
    <ThePopup>
      <h2>My Popup</h2>
    </ThePopup>
  </main>
</template>

<script>
import ThePopup from './components/ThePopup.vue';
export default {
  name: 'App',
  components: {
    ThePopup,
  },
  setup() {
    return {
      ThePopup,
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
