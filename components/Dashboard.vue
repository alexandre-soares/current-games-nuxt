<template>
  <div class="dashboard">
    <div class="dashboard__user">
      <img src="@/static/img/avatar.png" alt="avatar" />
      <h1>Alexandre Soares</h1>
      <p>Gamer by Passion</p>
    </div>
    <div class="dashboard__links">
      <div class="dashboard__link">
        <img src="@/static/img/icons/steam.svg" alt="steam" />
        <h2>Steam</h2>
      </div>
      <div class="dashboard__link">
        <img src="@/static/img/icons/ps4.svg" alt="ps4" />
        <h2>Playstation 4</h2>
      </div>
      <div class="dashboard__link">
        <img src="@/static/img/icons/switch.svg" alt="switch" />
        <h2>Nintendo Switch</h2>
      </div>
    </div>
    <div v-if="false" class="dashboard__social-codes">
      <div class="dashboard__code">
        <img src="@/static/img/icons/steam.svg" alt="steam" />
        <h2>Steam</h2>
      </div>
      <div class="dashboard__code">
        <img src="@/static/img/icons/ps4.svg" alt="ps4" />
        <h2>Playstation 4</h2>
      </div>
      <div class="dashboard__code">
        <img src="@/static/img/icons/switch.svg" alt="switch" />
        <h2>Nintendo Switch</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
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

    & h2 {
      padding: 0 2rem;
    }
  }

  &__social-codes {
    border-radius: 2rem;
  }

  &__code {
    display: flex;
    margin: 2rem 0;
    padding: 1rem 3rem;

    align-items: center;

    & h2 {
      padding: 0 2rem;
    }
  }
}
</style>
