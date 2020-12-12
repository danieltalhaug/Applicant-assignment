<template>
    <header class="header">
        <h1 class="header__logo">Cars2go</h1>
        <button>+ Add new car</button>
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
        background-color: #22313F;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .header__logo {
        color: white;
    }
</style>
