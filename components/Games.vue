<template>
  <div class="games">
    <div class="games__status">
      <h1>Active Games</h1>
      <input placeholder="Search *" type="text" name="" />
    </div>
    <div class="games__cards">
      <div class="card">
        <div class="card__img">
          <img
            src="@/static/img/games/ps4/ghost-of-tsushima.png"
            alt="ghost-tsushima"
          />
        </div>
        <div class="card__info">
          <h2>Ghost Of Tsushima</h2>
          <div class="progress-bar"></div>
        </div>
        <div class="card__completion">
          <h2 class="card__percentage">50%</h2>
        </div>
      </div>
      <div class="card">
        <div class="card__img">
          <img
            src="@/static/img/games/ps4/persona-5-royal.png"
            alt="ghost-tsushima"
          />
        </div>
        <div class="card__info">
          <h2>Persona 5 Royal</h2>
          <div class="progress-bar"></div>
        </div>
        <div class="card__completion">
          <h2 class="card__percentage">80%</h2>
        </div>
      </div>
      <div class="card">
        <div class="card__img">
          <img
            src="@/static/img/games/ps4/rise-of-the-tomb-raider.png"
            alt="ghost-tsushima"
          />
        </div>
        <div class="card__info">
          <h2>Rise of the Tomb Raider</h2>
          <div class="progress-bar"></div>
        </div>
        <div class="card__completion">
          <h2 class="card__percentage">20%</h2>
        </div>
      </div>
    </div>
    <Scroll-down-btn />
  </div>
</template>

<script>
import ScrollDownBtn from './ScrollDownBtn.vue'
export default {
  components: { ScrollDownBtn },
}
</script>

<style lang="scss" scoped>
.games {
  margin: 5rem;
  flex: 0 1 70%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;

  &__status {
    & input {
      background: linear-gradient(
        to right bottom,
        rgba(255, 255, 255, 0.7),
        rgba(255, 255, 255, 0.3)
      );
      border-radius: 2rem;
      border: none;
      width: 50%;
      padding: 1rem 2rem;
      margin: 1rem 0;

      &:focus {
        outline: none;
      }
    }
  }

  &__cards {
    overflow-y: scroll;
  }

  .card {
    display: flex;
    justify-content: space-between;
    background: linear-gradient(
      to left top,
      rgba(255, 255, 255, 1),
      rgba(255, 255, 255, 0.8)
    );

    border-radius: 2rem;
    margin: 2rem 0.5rem;
    padding: 2rem;
    // box-shadow: 6px 6px 20px rgba(122, 122, 122, 0.2);

    &__info {
      margin-left: 2rem;
      margin-right: 2rem;
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;

      & h2 {
        font-size: 2rem;
        font-weight: 600;
      }

      & .progress-bar {
        background: linear-gradient(
          to right top,
          $primary-color,
          $secondary-color
        );
        width: 100%;
        height: 25%;
        border-radius: 2rem;
        position: relative;
        overflow: hidden;

        &:after {
          content: '';
          width: 100%;
          height: 100%;
          background: rgb(236, 236, 236);
          position: absolute;
          left: 50%;
          margin: 0;
        }
      }
    }

    &__percentage {
      font-size: 3rem;
      font-weight: bold;
      background: linear-gradient(
        to right top,
        $primary-color,
        $secondary-color
      );
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
  }
}
</style>
