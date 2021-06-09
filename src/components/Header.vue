<template>
    <header>
        <nav>
            <a href="#">
                <img src="../assets/img/spotify.png" alt="Logo Spotify">
            </a>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    header {
        nav {
            padding: 10px 20px;
            background-color: $grey;

            img {
                max-width: 50px;
            }
        }
    }
</style>