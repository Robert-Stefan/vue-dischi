<template>
    <div id="app">
        <Header />

        <Musiclist />
    </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Musiclist from '@/components/Musiclist.vue';
export default {
    name: 'App',
    components: {
        Header,
        Musiclist,
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
    /*background-color: #1d2d3c;*/
}
</style>
