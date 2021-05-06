<template>
    <div v-if="!loading" class="music">
        <Music v-for="(music, index) in musicList" :key="index" :info="music" />
    </div>
    <div v-else class="loading">LOADING ...</div>
</template>

<script>
import axios from 'axios';
import Music from '@/components/Music.vue';

export default {
    name: 'Musiclist',
    components: {
        Music,
    },
    data() {
        return {
            apiURL: 'https://flynn.boolean.careers/exercises/api/array/music',
            musicList: [],
            loading: true,
        };
    },
    created() {
        this.getMusic();
    },
    methods: {
        getMusic() {
            /**
             * API CALL
             */
            axios
                .get(this.apiURL)
                .then(res => {
                    console.log(res.data.response);
                    this.musicList = res.data.response;
                    this.loading = false;
                })
                .catch(err => {
                    console.log('Error', err);
                });
        },
    },
};
</script>

<style scoped lang="scss">
.music {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    padding-top: 110px;
}

.loading {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 10%;
    color: #fff;
    font-weight: bold;
    font-size: 50px;
}
</style>
