<template>
    <div>
        <img :src="info.poster" :alt="info.title" />
        <h2>{{ info.title }}</h2>
        <p>{{ info.author }}</p>
        <p>{{ info.year }}</p>
        <p>{{ info.genre }}</p>
    </div>
</template>

<script>
export default {
    name: 'Music',
    props: ['info'],
};
</script>

<style scoped lang="scss"></style>
