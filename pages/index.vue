<template>
  <section class="glass"></section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.glass {
  background-color: white;
  min-height: 80vh;
  width: 70%;
  background: linear-gradient(
    to right bottom,
    rgba(255, 255, 255, 0.7),
    rgba(255, 255, 255, 0.3)
  );
  border-radius: 2rem;
  z-index: 2;
  backdrop-filter: blur(2rem);
}
</style>
