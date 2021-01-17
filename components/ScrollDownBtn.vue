<template>
  <section id="scroll-down" class="scroll-down-btn">
    <a><span></span></a>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.scroll-btn {
  @media only screen and (max-width: $bp-small) {
    display: none;
  }
}

/* SCROLL DOWN BTN */

.scroll-down-btn {
  z-index: 2;
  color: #fff;
  font: normal 400 20px/1 'Josefin Sans', sans-serif;
  letter-spacing: 0.1em;
  text-decoration: none;
  cursor: default;
  display: block;
  position: relative;
  transition: opacity 0.3s;
  height: 30px;
  margin-top: 15px;

  @media only screen and (max-width: $bp-small) {
    display: none;
  }
}

.scroll-down-btn span {
  position: absolute;
  top: 0;
  left: 50%;
  width: 30px;
  height: 50px;
  margin-left: -15px;
  border: 2px solid $primary-color;
  border-radius: 50px;
  box-sizing: border-box;
  //   transform: translateX(50%);
}

.scroll-down-btn span::before {
  position: absolute;
  top: 10px;
  left: 50%;
  content: '';
  width: 6px;
  height: 6px;
  margin-left: -3px;
  background-color: $secondary-color;
  border-radius: 100%;
  -webkit-animation: scroll-down-btn 2s infinite;
  animation: scroll-down-btn 2s infinite;
  box-sizing: border-box;
}

@-webkit-keyframes scroll-down-btn {
  0% {
    -webkit-transform: translate(0, 0);
    opacity: 0;
  }
  40% {
    opacity: 1;
  }
  80% {
    -webkit-transform: translate(0, 20px);
    opacity: 0;
  }
  100% {
    opacity: 0;
  }
}

@keyframes scroll-down-btn {
  0% {
    transform: translate(0, 0);
    opacity: 0;
  }
  40% {
    opacity: 1;
  }
  80% {
    transform: translate(0, 20px);
    opacity: 0;
  }
  100% {
    opacity: 0;
  }
}
@-webkit-keyframes scroll-down-btn {
  0% {
    -webkit-transform: translate(0, 0);
    opacity: 0;
  }
  40% {
    opacity: 1;
  }
  80% {
    -webkit-transform: translate(0, 20px);
    opacity: 0;
  }
  100% {
    opacity: 0;
  }
}

@keyframes scroll-down-btn {
  0% {
    transform: translate(0, 0);
    opacity: 0;
  }
  40% {
    opacity: 1;
  }
  80% {
    transform: translate(0, 20px);
    opacity: 0;
  }
  100% {
    opacity: 0;
  }
}
</style>
