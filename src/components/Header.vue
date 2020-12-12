<template>
    <header class="header">
        <h1 class="header__logo">Cars2go</h1>
        <button class="header__button">+ Add new car</button>
    </header>
</template>

<script>
export default {
  name: 'Header'
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
        padding: var(--spacing-medium);
    }
    .header__button {
        background: none;
        padding: var(--spacing-medium);
        border: none;
        color: white;
        font-size: 1em;
    }
    .header__button:hover {
        cursor: pointer;
        color: var(--grey-medium);
    }
</style>
