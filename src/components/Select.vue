<template>
    <select @change="changeType" id="select" class="form-select" aria-label="Default select example" v-model="genreName">
        <option selected>Seleziona un Genere</option>
        <option v-for="genre, index in genres" :key="index" :value="genre">{{ genre }}</option>
    </select>
</template>

<script>
export default {
    name: 'Select',
    data: function() {
        return {
            genres: [
                'Rock',
                'Pop',
                'Jazz',
                'Metal',
            ],
            genreName: 'Seleziona un Genere'
        }
    },
    computed: {

    },
    methods: {
        changeType:function () {
            console.log(this.genreName);
            this.$emit('changeGenre', this.genreName);
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    .form-select {
        display: inline-block;
        width: unset;
        min-width: 220px;
        cursor: pointer;
    }
</style>