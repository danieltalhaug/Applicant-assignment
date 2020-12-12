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
    padding: var(--spacing-small);
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.searchbar__field {
    padding: var(--spacing-small);
    width: 100%;
    border: 2px solid var(--grey-light);
    border-radius: var(--border-radius);
}
.searchbar__field::placeholder {
    color: var(--grey-medium);
}
.searchbar__button {
    padding: var(--spacing-small) 30px var(--spacing-small) 30px;
    margin-left: var(--spacing-small);
    background-color: var(--blue-dark);
    color: var(--grey-light);
    border-radius: var(--border-radius);
    border: solid 2px var(--blue-dark);
}
.searchbar__button:hover {
    background-color: var(--blue-medium);
    cursor: pointer;
}
</style>
