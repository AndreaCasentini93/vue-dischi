<template>
    <nav>
        <a href="#">
            <img src="../assets/img/spotify.png" alt="Logo Spotify">
        </a>
    </nav>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    nav {
        padding: 10px 20px;
        background-color: $grey;

        img {
            max-width: 50px;
        }
    }
</style>