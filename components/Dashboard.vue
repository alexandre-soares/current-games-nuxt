<template>
  <div class="dashboard">
    <div class="dashboard__user">
      <img src="@/static/img/avatar.png" alt="avatar" />
      <h1>Alexandre Soares</h1>
      <p>Gaming when not Coding</p>
    </div>
    <div class="dashboard__links">
      <div
        class="dashboard__link"
        :class="{ selected: selected == 1 }"
        @click="selectedConsole('PS4'), (selected = 1)"
      >
        <img src="@/static/img/icons/ps4.svg" alt="ps4" />
        <h2>Playstation 4</h2>
      </div>
      <div
        class="dashboard__link"
        :class="{ selected: selected == 2 }"
        @click="selectedConsole('Steam'), (selected = 2)"
      >
        <img src="@/static/img/icons/steam.svg" alt="steam" />
        <h2>Steam</h2>
      </div>
      <div
        class="dashboard__link"
        :class="{ selected: selected == 3 }"
        @click="selectedConsole('Switch'), (selected = 3)"
      >
        <img src="@/static/img/icons/switch.svg" alt="switch" />
        <h2>Nintendo Switch</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    selectedConsole(name) {
      this.$emit('clicked', name)
    },
  },
}
</script>

<style lang="scss" scoped>
.dashboard {
  background: linear-gradient(
    to right bottom,
    rgba(255, 255, 255, 0.7),
    rgba(255, 255, 255, 0.3)
  );
  border-top-left-radius: 2rem;
  border-bottom-left-radius: 2rem;
  flex: 0 0 30%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  text-align: center;
  padding: 2rem 0;

  @media only screen and (max-width: $bp-large) {
    flex: 0 1 100%;
    border-radius: 2rem;
  }

  &__user {
    & h1 {
      font-size: 2rem;
      margin: 2rem 0;
    }

    & p {
      font-size: 1.6rem;
      color: $secondary-color-text;
      font-weight: 600;
    }
  }

  &__link {
    display: flex;
    margin: 2rem 0;
    padding: 1rem 3rem;
    align-items: center;
    cursor: pointer;

    &.selected h2 {
      font-weight: bold;
    }

    & h2 {
      padding: 0 2rem;
    }
  }

  // &__colors {
  //   display: flex;
  //   margin: 0.5rem 0;
  //   align-items: center;
  //   justify-content: space-between;
  //   z-index: 99;

  //   & span {
  //     height: 4rem;
  //     width: 4rem;
  //     margin: 0.5rem;
  //     border-radius: 0.5rem;
  //     cursor: pointer;
  //   }
  // }
}

// .colors {
//   &--1 {
//     background: linear-gradient(to right top, $primary-color, $secondary-color);
//   }
//   &--2 {
//     background: linear-gradient(
//       to right top,
//       $primary-2-color,
//       $secondary-2-color
//     );
//   }
//   &--3 {
//   }
//   &--4 {
//   }
// }
</style>
