<template>
    <article class="card">
    </article>
</template>

<script>
export default {
  name: 'RentalCards',
  props: {
    title: String,
    price: Number,
    image: String,
    persons: Number,
    doors: Number,
    liters: Number,
    description: String
  }
}
</script>

<style scoped>
.card {
    display: flex;
}
</style>
