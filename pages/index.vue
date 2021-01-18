<template>
  <section class="glass">
    <Dashboard @clicked="onClickChild" />
    <Games :selected-console="selectedConsole" />
  </section>
</template>

<script>
import Dashboard from '../components/Dashboard.vue'
import Games from '../components/Games.vue'
export default {
  components: { Dashboard, Games },
  data() {
    return {
      selectedConsole: 'PS4',
    }
  },
  methods: {
    onClickChild(value) {
      this.selectedConsole = value
    },
  },
}
</script>

<style lang="scss" scoped>
.glass {
  background-color: white;
  height: 80vh;
  width: 70%;
  background: linear-gradient(
    to right bottom,
    rgba(255, 255, 255, 0.7),
    rgba(255, 255, 255, 0.3)
  );
  border-radius: 2rem;
  z-index: 2;
  backdrop-filter: blur(2rem);

  display: flex;

  @media only screen and (max-width: $bp-large) {
    flex-direction: column;
    height: auto;
    min-height: auto;
    margin: 2rem 0;
  }

  @media only screen and (max-width: $bp-medium) {
    width: 95%;
  }
}
</style>
