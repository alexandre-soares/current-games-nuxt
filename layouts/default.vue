<template>
  <div class="background">
    <div class="x">
      <div class="background__circle-1 y"></div>
    </div>
    <Nuxt />
  </div>
</template>

<style lang="scss">
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

  @media only screen and (max-width: $bp-large) {
    font-size: 50%;
  }

  @media only screen and (max-width: $bp-medium) {
    font-size: 58%;
  }

  @media only screen and (max-width: $bp-small) {
    font-size: 56%;
  }
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

body {
  height: 100vh;
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
    top: 5%;
    left: 5%;
  }
}

h1 {
  color: $primary-color-text;
  font-weight: 600;
  font-size: 3rem;
  opacity: 0.8;
}

h2 {
  color: $secondary-color-text;
  font-weight: 500;
  opacity: 0.8;
}

h3 {
  color: $primary-color-text;
  font-weight: 600;
  opacity: 0.8;
}

$size: 300px;

.x {
  animation: x 250s linear infinite alternate;
}

.y {
  animation: y 140s linear infinite alternate;
}

@keyframes x {
  100% {
    transform: translateX((calc(100vw - #{$size})));
  }
}

@keyframes y {
  100% {
    transform: translateY(calc(100vh - #{$size}));
  }
}
</style>
