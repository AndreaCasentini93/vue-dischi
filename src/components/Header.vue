<template>
    <header>
        <nav>
            <a href="#">
                <img :src="image" alt="Logo Spotify">
            </a>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'Header',
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