<template>
    <header>
        <nav>
            <a href="#">
                <img :src="image" alt="Logo Spotify">
            </a>
            <Select @changeGenre="changeType"/>
        </nav>
    </header>
</template>

<script>
import Select from './Select.vue';

export default {
    name: 'Header',
    components: {
        Select
    },
    props: {
        image: String
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
            @include flex-centering('vertical');
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