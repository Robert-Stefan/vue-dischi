<template>
    <div class="album">
        <div class="poster">
            <a :href="info.title">
                <img :src="info.poster" :alt="info.title" />
            </a>
        </div>
        <div class="title">
            <a :href="info.title">{{ info.title }}</a>
        </div>
        <div class="author">
            <a :href="info.author">{{ info.author }}</a>
        </div>
        <div class="year">{{ info.year }}</div>
        <div class="genre">{{ info.genre }}</div>
    </div>
</template>

<script>
export default {
    name: 'Music',
    props: ['info'],
};
</script>

<style scoped lang="scss">
.album {
    display: flex;
    flex-direction: column;
    padding: 15px;
    margin: 10px 30px;
    flex-basis: calc((100% / 10) - 13px);
    border-radius: 5px;
    background-color: #2e3a46;
    text-align: center;

    .poster {
        width: 100%;
        height: 150px;

        img {
            height: 100%;
            width: 100%;
            border-radius: 5px;
            cursor: pointer;
        }
    }

    .title {
        padding: 20px 0;
        font-size: 20px;
        text-transform: uppercase;
        cursor: pointer;

        a {
            text-decoration: none;
            color: #fff;
        }
    }

    .author {
        a {
            text-decoration: none;
            color: #7b7b7d;
        }
    }

    .year {
        padding: 10px 0;
        color: #7b7b7d;
    }

    .genre {
        color: #fff;
    }
}
</style>
