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
            authorName: 'Seleziona un Autore'
        }
    },
    computed: {
        authors: function() {
            return this.array
        }
    },
    props: {
        array: Array
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

    @include select;
    
</style>