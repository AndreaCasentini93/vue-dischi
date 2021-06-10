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
            genreName: 'Seleziona un Genere'
        }
    },
    computed: {
        genres: function() {
            return this.array
        }
    },
    props: {
        array: Array
    },
    methods: {
        changeType:function () {
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
        max-height: 38px;
        margin-right: 30px;
        cursor: pointer;
    }
</style>