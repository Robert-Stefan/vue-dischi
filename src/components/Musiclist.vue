<template>
    <section>
        <Select @changed="filteredGenre" />
        <div v-if="!loading" class="music">
            <Music
                v-for="(music, index) in newList"
                :key="index"
                :info="music"
            />
        </div>
        <div v-else class="loading">LOADING ...</div>
    </section>
</template>

<script>
import axios from 'axios';
import Music from '@/components/Music.vue';
import Select from '@/components/Select.vue';

export default {
    name: 'Musiclist',
    components: {
        Music,
        Select,
    },
    data() {
        return {
            apiURL: 'https://flynn.boolean.careers/exercises/api/array/music',
            musicList: [],
            loading: true,
            genreSelected: 'all',
        };
    },
    computed: {
        newList() {
            if (this.genreSelected === 'all') {
                return this.musicList;
            }

            return this.musicList.filter(album => {
                return (
                    album.genre.toLowerCase() ===
                    this.genreSelected.toLowerCase()
                );
            });
        },
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
                    //console.log(res.data.response);
                    this.musicList = res.data.response;
                    this.loading = false;
                })
                .catch(err => {
                    console.log('Error', err);
                });
        },
        filteredGenre(select) {
            //console.log(this.genreSelected);
            this.genreSelected = select;
        },
    },
};
</script>

<style scoped lang="scss">
.music {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
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
