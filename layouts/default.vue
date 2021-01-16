<template>
  <div class="background">
    <div class="background__circle-1"></div>
    <div class="background__circle-2"></div>
    <Nuxt />
  </div>
</template>

<style lang="scss">
// Breakpoints

$bp-largest: 75em; // 1200px
$bp-large: 68.75em; // 1100px
$bp-medium: 56.25em; // 900px
$bp-small: 37.5em; // 600px
$bp-smallest: 31.25em; // 500px

// Colors

$primary-color: #ff706c;
$secondary-color: #ff935e;

html {
  font-family: 'Poppins', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  font-size: 62.5%;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.background {
  min-height: 100vh;
  background: linear-gradient(to right top, $primary-color, $secondary-color);
  display: flex;
  align-items: center;
  justify-content: center;

  &__circle-1,
  &__circle-2 {
    background-color: white;
    background: linear-gradient(
      to right bottom,
      rgba(255, 255, 255, 0.8),
      rgba(255, 255, 255, 0.3)
    );
    height: 30rem;
    width: 30rem;
    border-radius: 50%;
    position: absolute;
    z-index: 1;
  }

  &__circle-1 {
    bottom: 5%;
    left: 5%;
  }

  &__circle-2 {
    top: 3%;
    right: 8%;
  }
}
</style>
