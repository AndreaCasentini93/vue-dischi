<template>
    <select @change="changeName" id="select" class="form-select" aria-label="Default select example" v-model="authorName">
        <option selected>Seleziona un Autore</option>
        <option v-for="author, index in authors" :key="index" :value="author">{{ author }}</option>
    </select>
</template>

<script>
export default {
    name: 'SelectAuthor',
    data: function() {
        return {
            authors: [
                'Bon Jovi',
                'Queen'
            ],
            authorName: 'Seleziona un Autore'
        }
    },
    computed: {

    },
    methods: {
        changeName:function () {
            this.$emit('changeAuthor', this.authorName);
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
        cursor: pointer;
    }
</style>