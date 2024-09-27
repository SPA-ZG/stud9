<template>
  <main>
    <h1 class="text-title">Naša kolekcija</h1>

    <p class="text-description">
      Predstavljamo Vam najveću kolekciju biljaka, uključujući unutarnje i vanjske vrste. Odaberite
      svoju jedinstvenu biljku.
    </p>

    <ul>
      <li class="buttons">
        <button type="button" autofocus class="btn-style" @click="filterCard(false)">
          Svi proizvodi
        </button>

        <button type="button" class="btn-style" @click="filterCard(true)">Dostupno sada</button>
      </li>
    </ul>

    <section class="card-container">
      <ProductCard
        v-for="card in cardDetails"
        :key="card.id"
        :card-title="card.name"
        :card-img-src="card.image"
        :card-price="card.price"
        :card-available="card.available"
      />
    </section>
  </main>
</template>

<script>
import ProductCard from './ProductCard.vue'

export default {
  data() {
    return {
      cardData: {},
      cardDetails: [],
      btnFocus: null
    }
  },
  components: {
    ProductCard
  },
  beforeMount() {
    this.getCardDetails()
  },
  methods: {
    async getCardDetails() {
      try {
        const response = await import('../data/data.json')
        this.cardData = response.default || response
        this.cardDetails = this.cardData
      } catch (error) {
        console.error('Error fetching data:', error)
      }
    },
    async filterCard(availableCard) {
      console.log('Filter plants...')
      this.cardDetails = this.cardData

      if (availableCard === true) {
        this.cardDetails = this.cardDetails.filter((card) => {
          return card.available === availableCard
        })
      } else {
        return
      }
    }
  }
}
</script>

<style scoped>
.text-title {
  position: relative;
  font-size: 2rem;
  font-weight: 700;
  color: var(--heading-text-clr);
  font-family: var(--font-family);
  margin-bottom: 1rem;
  text-align: center;
  color: var(--heading-text-clr);
}

.text-description {
  max-width: 26rem;
  margin-bottom: 1rem;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
}

.buttons {
  display: flex;
  gap: 1.5rem;
  align-items: center;
  justify-content: center;
}

.btn-style {
  border: none;
  outline: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
  color: var(--heading-text-clr);
  background-color: var(--main-bg-clr);
  border-radius: 0.25rem;
  font-size: 1rem;
  margin-bottom: 1rem;
}

.btn-style:hover,
.btn-style:focus {
  background-color: var(--btn-bg-clr);
}

.card-container {
  margin-top: 2rem;
  display: grid;
  gap: 2rem;
  grid-template-columns: repeat(auto-fill, minmax(min(100%, 16.25rem), 1fr));
  margin-top: 2rem;
}
</style>
