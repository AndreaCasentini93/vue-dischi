<template>
    <section id="discs_list" v-if="!loading">
        <div class="my_container">
            <Disc v-for="disc, index in selectedDiscs" :key="index" :card="disc" />
        </div>
    </section>
    <Loading msg="Vue Dischi App" v-else />
</template>

<script>
import axios from 'axios';
import Disc from './Disc.vue';
import Loading from './Loading.vue';

export default {
    name: 'DiscsList',
    components: {
        Disc,
        Loading
    },
    data: function() {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            discs: [],
            loading: true
        }
    },
    computed: {
        genresArray: function() {
            let newArray = [];
            this.discs.forEach((element) => {
                if (!newArray.includes(element.genre)) {
                    newArray.push(element.genre);
                }
            });
            return newArray;
        },
        authorsArray: function() {
            let newArray = [];
            this.discs.forEach((element) => {
                if (!newArray.includes(element.author)) {
                    newArray.push(element.author);
                }
            });
            return newArray;
        },
        musicGenre: function() {
            return this.discsGenre
        },
        selectedDiscs: function() {

            if (this.musicGenre == '' || this.musicGenre == 'Seleziona un Genere') {
                    return this.discs;
            }

            return this.discs.filter ((element) => {
                return element.genre == this.musicGenre;
            })

        }
    },
    props: {
        discsGenre: String
    },
    created: function() {
        axios
            .get(this.apiUrl)
            .then((response) => {
                this.discs = response.data.response;
                this.loading = false;
            })
            .catch()
    },
    destroyed: function() {
        this.$emit('newArray', this.genreArray);
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    #discs_list {
        min-height: calc(100vh - 70px);
        background-color: $blue;

        .my_container {
            display: flex;
            @include flex-centering('horizontal');
            align-content: center;
            flex-wrap: wrap;
            max-width: calc(1170px + 40px);
            padding: 50px;
        }
    }
</style>