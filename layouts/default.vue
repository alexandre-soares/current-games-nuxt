<template>
  <div class="background">
    <div class="x">
      <div class="background__circle-1 y"></div>
    </div>

    <div class="circle-background circle-background--1"></div>
    <div class="circle-background circle-background--2"></div>
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

  transition: background 0.3s ease-in;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

body {
  height: 100vh;
  overflow: hidden;

  @media only screen and (max-width: $bp-large) {
    overflow: auto;
  }
}

.background {
  min-height: 100vh;
  background: linear-gradient(to right top, $primary-color, $secondary-color);
  display: flex;
  align-items: center;
  justify-content: center;

  @media only screen and (max-width: $bp-large) {
    height: auto;
    min-height: auto;
  }

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
  &__circle-2 {
    bottom: 5%;
    right: 5%;
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
  animation: x 150s linear infinite alternate;
}

.y {
  animation: y 80s linear infinite alternate;
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

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

.circle-background {
  position: absolute;
  width: 70rem;
  height: 70rem;
  border-radius: 50%;
  background: linear-gradient(
    to right top,
    $primary-circle-color,
    $secondary-circle-color
  );
  filter: blur(10rem);

  &--1 {
    bottom: -10%;
    left: -10%;
  }
  &--2 {
    top: -10%;
    right: -10%;
    transform: rotate(90deg);
  }
}
</style>
