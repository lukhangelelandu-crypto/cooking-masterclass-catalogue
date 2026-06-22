<template>
    <header>
        <h1>Cooking Masterclass</h1>
        <p>Wishlist: {{ count }}</p>
    </header>
</template>

<script>
export default {
    props: ["count"]
};
</script>

<style>
header {
    display: flex;
    justify-content: space-between;
    padding: 1rem;
    background: #f8f8f8;
}
</style>