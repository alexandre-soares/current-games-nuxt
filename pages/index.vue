<template>
  <section class="glass">
    <Dashboard />
    <Games />
  </section>
</template>

<script>
import Dashboard from '../components/Dashboard.vue'
import Games from '../components/Games.vue'
export default {
  components: { Dashboard, Games },
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
}
</style>
