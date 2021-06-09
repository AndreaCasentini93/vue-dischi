<template>
    <section class="container">
        <Disc />
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

    }
</style>