<template>
    <header class="container">
        <img src="@/assets/logo.png" alt="logo" />
    </header>
</template>

<script>
export default {
    name: 'Header',
};
</script>

<style scoped lang="scss">
.container {
    height: 60px;
    display: flex;
    background-color: #2e3a46;
    img {
        padding: 5px;
    }
}
</style>
