<template>
    <div class="header">
        <h1 class="header__logo">Cars2go</h1>
        <button @click="openModal" class="header__button">+ Add new car</button>
    </div>
</template>

<script>
export default {
  name: 'Header',
  methods: {
    openModal () {
      this.$emit('openModal', true)
    }
  }
}
</script>

<style scoped>
    .header {
        height: 100px;
        background-color: var(--blue-dark);
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .header__logo {
        color: white;
        padding: var(--spacing-small);
    }
    .header__button {
        background: none;
        padding: var(--spacing-small);
        border: none;
        color: white;
        font-size: 1em;
    }
    .header__button:hover {
        cursor: pointer;
        color: var(--blue-medium);
    }
</style>
