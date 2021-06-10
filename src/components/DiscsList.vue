<template>
    <section id="discs_list" v-if="!loading">
        <Select @changeGenre="changeType"/>
        <div class="my_container">
            <Disc v-for="disc, index in discs" :key="index" :card="disc" />
        </div>
    </section>
    <Loading msg="Vue Dischi App" v-else />
</template>

<script>
import axios from 'axios';
import Disc from './Disc.vue';
import Loading from './Loading.vue';
import Select from './Select.vue';

export default {
    name: 'DiscsList',
    components: {
        Disc,
        Loading,
        Select
    },
    data: function() {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            discs: [],
            loading: true,
            musicGenre: ''
        }
    },
    computed: {
        selectedDiscs: function() {

            if (this.musicGenre == '' || this.musicGenre == 'Seleziona un Genere') {
                    return this.discs;
            }

            return this.discs.filter ((element) => {
                return element.genre == this.musicGenre;
            })

        }
    },
    methods: {
        changeType: function(genre) {
            this.musicGenre = genre;
            console.log(this.musicGenre);
            console.log(this.selectedDiscs);
        }
    },
    created: function() {
        axios
            .get(this.apiUrl)
            .then((response) => {
                this.discs = response.data.response;
                this.loading = false;
            })
            .catch()
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    #discs_list {
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