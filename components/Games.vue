<template>
  <div class="games">
    <div class="games__status">
      <h1>Active Games - {{ selectedConsole }}</h1>
      <input v-model="query" placeholder="Search *" type="text" />
    </div>
    <div class="games__cards">
      <transition-group name="fade" appear mode="out-in">
        <span
          v-for="(game, index) in filterGames"
          :key="index"
          tag="div"
          class="card"
        >
          <div class="card__img">
            <img :src="game.img" :alt="game.name" />
          </div>
          <div class="card__info">
            <h2>{{ game.name }}</h2>
            <div class="progress-bar">
              <div
                class="progress-bar--percentage"
                :style="'left:' + game.percentage + '%'"
              ></div>
            </div>
          </div>
          <div class="card__completion">
            <h2 class="card__percentage">{{ game.percentage }}%</h2>
          </div>
        </span>
      </transition-group>
    </div>
    <Scroll-down-btn v-if="filterGames.length > 2" />
  </div>
</template>

<script>
import ScrollDownBtn from './ScrollDownBtn.vue'
export default {
  components: { ScrollDownBtn },
  props: {
    selectedConsole: {
      type: String,
      default: 'PS4',
    },
  },
  data() {
    return {
      query: '',
      console: 'PS4',
      games: [
        {
          name: 'Ghost of Tsushima',
          console: 'PS4',
          percentage: 70,
          img: require('@/static/img/games/ps4/ghost-of-tsushima.png'),
        },
        {
          name: `Marvel Spiderman`,
          console: 'PS4',
          percentage: 95,
          img: require('@/static/img/games/ps4/spiderman.png'),
        },
        {
          name: 'Rise of The Tomb Raider',
          console: 'PS4',
          percentage: 30,
          img: require('@/static/img/games/ps4/rise-of-the-tomb-raider.png'),
        },
        {
          name: 'Persona 5 Royal',
          console: 'PS4',
          percentage: 80,
          img: require('@/static/img/games/ps4/persona-5-royal.png'),
        },
        {
          name: 'Mario Odyssey',
          console: 'Switch',
          percentage: 80,
          img: require('@/static/img/games/switch/mario-odyssey.png'),
        },
        {
          name: 'The Legend of Zelda - Breath of The Wild',
          console: 'Switch',
          percentage: 50,
          img: require('@/static/img/games/switch/breath-of-the-wild.png'),
        },
        {
          name: 'Astral Chain',
          console: 'Switch',
          percentage: 40,
          img: require('@/static/img/games/switch/astral-chain.png'),
        },
        {
          name: 'Code Vein',
          console: 'Steam',
          percentage: 80,
          img: require('@/static/img/games/steam/code-vein.png'),
        },
        {
          name: 'Cyberpunk 2077',
          console: 'Steam',
          percentage: 80,
          img: require('@/static/img/games/steam/cyberpunk.png'),
        },
        {
          name: 'Metal Gear Solid V',
          console: 'Steam',
          percentage: 80,
          img: require('@/static/img/games/steam/mgsv.png'),
        },
        {
          name: 'Monster Hunter World',
          console: 'Steam',
          percentage: 95,
          img: require('@/static/img/games/steam/mhw.png'),
        },
      ],
    }
  },
  computed: {
    computedList() {
      const vm = this
      return this.games.filter(function (item) {
        return item.name.toLowerCase().includes(vm.query.toLowerCase())
      })
    },
    filterGames() {
      return this.filterGamesByName(this.filterGamesByCategory(this.games))
    },
  },
  watch: {
    selectedConsole(newVal, oldVal) {
      // watch it
      console.log('Prop changed: ', newVal, ' | was: ', oldVal)
      this.console = newVal
    },
  },
  methods: {
    filterGamesByCategory(games) {
      console.log('filter by console')
      return games.filter((game) => !game.console.indexOf(this.console))
    },

    filterGamesByName(games) {
      console.log('filter by name')
      return games.filter((game) =>
        game.name.toLowerCase().includes(this.query.toLowerCase())
      )
    },
  },
}
</script>

<style lang="scss" scoped>
.games {
  margin: 5rem;
  flex: 0 1 70%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;

  @media only screen and (max-width: $bp-large) {
    flex: 0 1 100%;
  }

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
    @media only screen and (max-width: $bp-medium) {
      margin-left: -4rem;
      margin-right: -4rem;
    }
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

    &__img {
      @media only screen and (max-width: $bp-medium) {
        width: 15%;
      }
      & img {
        width: 100%;
      }
    }

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

        @media only screen and (max-width: $bp-medium) {
          font-size: 1.4rem;
        }
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
        margin: 0;
        margin-bottom: -1px;
      }

      & .progress-bar--percentage {
        content: '';
        width: 100%;
        height: 100%;
        background: rgb(236, 236, 236);
        position: absolute !important;
        margin: 0;
      }
    }

    &__percentage {
      font-size: 3rem;
      font-weight: bold;
      background: linear-gradient(to right top, #652020, #e8568e);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;

      @media only screen and (max-width: $bp-medium) {
        font-size: 2rem;
      }
    }
  }
}
</style>
