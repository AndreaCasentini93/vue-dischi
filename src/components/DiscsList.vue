<template>
    <section>
        <div class="my_container">
            <Disc v-for="disc, index in discs" :key="index" />
        </div>
    </section>
</template>

<script>
import axios from 'axios';
import Disc from './Disc.vue';

export default {
    name: 'DiscsList',
    components: {
        Disc
    },
    data: function() {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            discs: []
        }
    },
    created: function() {
        axios
            .get(this.apiUrl)
            .then((response) => {
                this.discs = response.data.response;
            })
            .catch()
  }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    section {
        height: calc(100vh - 70px);
        background-color: $blue;

        .my_container {
            display: flex;
            @include flex-centering;
            align-content: center;
            flex-wrap: wrap;
            height: 100%;
            color: white;
        }
    }
</style>