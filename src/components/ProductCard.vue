<template>
  <article>
    <div>
      <img :src="cardImgSrc" alt="Plant Image" class="image" />
    </div>
    <div class="mt-3">
      <div class="line">
        <h3 class="title">{{ cardTitle }}</h3>

        <div class="price">
          {{ cardPrice }}
        </div>
      </div>

      <div class>
        <p v-if="!cardAvailable" class="sold-out">Prodano</p>
      </div>
    </div>
  </article>
</template>

<script setup>
defineProps({ cardImgSrc: String, cardTitle: String, cardPrice: String, cardAvailable: Boolean })
</script>

<style scoped>
.sold-out {
  color: var(--sold-out-text-clr);
  margin-top: 0.5rem;
  display: flex;
  align-items: center;
}

.image {
  border-radius: 1rem;
  width: 260px;
  height: 160px;
  object-fit: cover;
}

.mt-3 {
  margin-top: 0.75rem;
}

.line {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.title {
  font-size: 1rem;
  color: var(--heading-text-clr);
}

.price {
  padding: 0.1875rem 0.5rem;
  border-radius: 0.25rem;
  font-size: 0.875rem;
}
</style>
