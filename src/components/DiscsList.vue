<template>
    <section id="discs_list" v-if="!loading">
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
    created: function() {
        axios
            .get(this.apiUrl)
            .then((response) => {
                this.discs = response.data.response;
                // this.loading = false;
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
            height: 100%;
            padding: 50px 0;
        }
    }
</style>