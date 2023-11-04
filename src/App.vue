<template>
  <main>
    <h1>Vue Popups</h1>
    <button @click="() => TogglePopup('buttonTrigger')">Open Popup</button>
    <ThePopup v-if="popupTriggers.buttonTrigger" :TogglePopup="() => TogglePopup('buttonTrigger')">
      <h2>My Button Popup</h2>
    </ThePopup>
    <ThePopup v-if="popupTriggers.timedTrigger">
      <h2>My Timed Popup</h2>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam dicta rem, esse pariatur
        consequatur dolorum officia asperiores doloribus molestias ratione exercitationem voluptas
        incidunt? Natus accusamus, aliquam eveniet hic ab porro.
      </p>
    </ThePopup>
  </main>
</template>

<script>
import { ref } from 'vue';
import ThePopup from './components/ThePopup.vue';
export default {
  name: 'App',
  components: {
    ThePopup,
  },
  setup() {
    const popupTriggers = ref({
      buttonTrigger: false,
      timedTrigger: false,
    });

    const TogglePopup = (trigger) => {
      popupTriggers.value[trigger] = !popupTriggers.value[trigger]
    }

    return {
      ThePopup,
      popupTriggers,
      TogglePopup,
    };
  },
};
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
