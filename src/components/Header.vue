<template>
    <header>
        <nav>
            <a href="#">
                <img :src="image" alt="Logo Spotify">
            </a>
            <div>
                <Select @changeGenre="changeType" :array="genresArrayImport"/>
                <SelectAuthors @changeAuthor="changeName" :array="authorsArrayImport"/>
            </div>
        </nav>
    </header>
</template>

<script>
import Select from './Select.vue';
import SelectAuthors from './SelectAuthors.vue';

export default {
    name: 'Header',
    components: {
        Select,
        SelectAuthors
    },
    data: function() {
        return {
            discsGenre: '',
            discsAuthor: ''
        }
    },
    computed: {
        genresArrayImport: function() {
            return this.genresArray
        },
        authorsArrayImport: function() {
            return this.authorsArray
        }
    },
    methods: {
        changeType: function(genre) {
            this.discsGenre = genre;
            this.$emit('discsGenre', this.discsGenre);
        },
        changeName: function(author) {
            this.discsAuthor = author;
            this.$emit('discsAuthor', this.discsAuthor);
        }
    },
    props: {
        image: String,
        genresArray: Array,
        authorsArray: Array
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    header {
        nav {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            @include flex-centering(vertical);
            padding: 10px 20px;
            background-color: $dark-grey;

            a {
                img {
                    max-width: 50px;
                    transition: filter .3s linear;

                    &:hover {
                        filter: brightness(130%);
                    }
                }
            }
        }
    }
</style>