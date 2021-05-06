<template>
    <section class="music">
        <div v-if="!loading">
            <div v-for="music in musicList" :key="music.id">
                <Music :info="music" />
            </div>
        </div>
        <div v-else class="loader">Loading...</div>
    </section>
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
                    console.log(res.data);
                    this.musicList = res.data;
                    this.loading = false;
                })
                .catch(err => {
                    console.log('Error', err);
                });
        },
    },
};
</script>

<style></style>
