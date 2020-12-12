<template>
  <div id="app">
    <header>
      <Header/>
      <Searchbar
        @getSearchWord="setSearchInputValue"
      />
    </header>
    <main>
      <section v-if="filterCards.length">
         <div class="cards-container" v-for="(card, index) in filterCards" :key="index">
          <RentalCards
            :title="card.title"
            :price="card.price"
            :image="card.imageUrl"
            :persons="card.persons"
            :doors="card.doors"
            :liters="card.liters"
            :description="card.description"
          />
        </div>
        <span class="cards-counter">Showing {{filterCards.length}} results</span>
      </section>
      <section v-else>
        <p class="cards-error">{{ errorMessage }}</p>
      </section>
    </main>
  </div>
</template>

<script>
// imported components
import Header from './components/Header.vue'
import Searchbar from './components/Searchbar.vue'
import RentalCards from './components/RentalCards.vue'

export default {
  name: 'App',
  components: {
    Header,
    Searchbar,
    RentalCards
  },
  data () {
    return {
      cards: [
        {
          title: '2020 Toyota GR Yaris',
          price: 1900,
          imageUrl: 'https://www.netcarshow.com/Toyota-GR_Yaris-2021-1600-98.jpg',
          persons: 2,
          doors: 3,
          liters: 1.5,
          description: 'When Toyota announced its return to the World Rally Championship in 2015, the concept of building a rally-inspired sports car was part of the plan. The vision was to take technical knowledge and experience from the highest level of international competition and apply them to a new road car that is also suitable for competition driving, and an affordable proposition for customers.'
        },
        {
          title: '2021 Volkswagen Golf R',
          price: 1200,
          imageUrl: 'https://www.netcarshow.com/Volkswagen-Golf_R-2022-1600-12.jpg',
          persons: 5,
          doors: 5,
          liters: 0.6,
          description: 'Volkswagen unveiled the latest generation of the brand\'s performance halo, the new Golf R. This car boasts 315 horsepower, 27 more than the outgoing U.S. model, as well as 310 pound-feet of torque. With standard 4Motion® all-wheel drive, the Volkswagen Golf R can sprint from 0 to 62 mph in just 4.7 seconds, on its way to a top track speed of 155 mph. The car will go on sale in the U.S. as a 2022 model during the latter part of 2021.'
        },
        {
          title: '2021 Nissan Kicks',
          price: 1800,
          imageUrl: 'https://www.netcarshow.com/Nissan-Kicks-2021-1600-08.jpg',
          persons: 5,
          doors: 5,
          liters: 0.7,
          description: 'Nissan Kicks compact crossover quickly established a reputation for offering an impressive array of class-leading features with equally attractive value. Introduced three years ago in the U.S. as the entry model to Nissan\'s lineup of six crossovers and SUVs, Kicks has attracted young, enthusiastic new buyers to the brand.'
        }
      ],
      searchQuery: '',
      errorMessage: 'Can\'t find a car based on your search, please try a different search.'
    }
  },
  computed: {
    filterCards: function () {
      // Filters cards based on search input from user and returns it
      return this.cards.filter((card) => {
        return card.title.toLowerCase().includes(this.searchQuery.toLowerCase())
      })
    }
  },
  methods: {
    setSearchInputValue (searchword) {
      // Gets the searchword from searchbar component and saves it. No mutated props!
      this.searchQuery = searchword
    }
  }
}
</script>

<style>
:root {
  --blue-dark: #22313F;
  --blue-medium: #486885;
  --grey-light: #F6F6F6;
  --grey-medium: #A3A3A3;
  --green-medium: #5DAC6E;
  --spacing-small: 10px;
  --spacing-medium: 20px;
  --border-radius: 5px;
  --text-small: .8em;
  --text-medium: 1em;
  --text-large: 2em;
  --text-huge: 3em;
  --weight-heavy: 600;
  --weight-medium: 400;
  --weight-light: 300;
}
html {
  box-sizing: border-box;
  font-family: Roboto;
}

*, *:before, *:after {
  box-sizing: inherit;
}
#app {
  margin: 0 auto;
  max-width: 1200px;
}

body, h1, h2, h3, h4, h5, h6, p, ol, ul {
  margin: 0;
  padding: 0;
  font-weight: normal;
  color: var(--blue-dark);
}

ol, ul {
  list-style: none;
}

img {
  max-width: 100%;
  height: auto;
}
main {
  background-color: var(--grey-light);
  padding: var(--spacing-small);
  min-height: 100vh;
}
.cards-counter {
  display: flex;
  justify-content: flex-end;
}
.cards-error {
  text-align: center;
  color: var(--blue-dark);
  font-size: var(--text-medium);
  padding-top: 50px;
}
</style>
