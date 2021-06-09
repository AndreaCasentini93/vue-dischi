<template>
    <div>
        main
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'DiscsList',
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

</style>