<template>
    <div id="app">
        <Header />

        <Music />
    </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Music from '@/components/Music.vue';
export default {
    name: 'App',
    components: {
        Header,
        Music,
    },
};
</script>

<style lang="scss">
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: sans-serif;
    background-color: #1d2d3c;
}
</style>
