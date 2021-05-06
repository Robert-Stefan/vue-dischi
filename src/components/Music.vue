<template>
    <div class="album">
        <div class="image">
            <img :src="info.poster" :alt="info.title" />
        </div>
        <div class="title">{{ info.title }}</div>
        <div class="artist">{{ info.author }}</div>
        <div class="year">{{ info.year }}</div>
        <div class="genre">{{ info.genre }}</div>
    </div>
</template>

<script>
export default {
    name: 'Music',
    props: ['info',],
};
</script>

<style scoped lang="scss">


</style>
