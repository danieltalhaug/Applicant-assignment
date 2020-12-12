<template>
    <form class="searchbar">
      <input class="searchbar__field" type="text" placeholder="Search" name="search">
      <button class="searchbar__button" type="submit">Search</button>
    </form>
</template>

<script>
export default {
  name: 'Searchbar'
}
</script>

<style scoped>
.searchbar {
    padding: var(--spacing-medium);
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.searchbar__field {
    padding: var(--spacing-medium);
    width: 100%;
    border: 2px solid var(--grey-light);
    border-radius: var(--border-radius);
}
.searchbar__button {
    padding: var(--spacing-medium) 30px var(--spacing-medium) 30px;
    margin-left: var(--spacing-medium);
    background-color: var(--blue-dark);
    color: var(--grey-light);
    
}
</style>
