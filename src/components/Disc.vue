<template>
    <div class="text-center">
        <img class="img-fluid" src="https://www.zeusnews.it/img/4/8/1/6/2/0/026184-620-google-vedi-immagini.jpg" alt="">
        <h4>Titolo</h4>
        <h6>Sottotitolo</h6>
    </div>
</template>

<script>
export default {
    name: 'Disc'
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    div {
        width: calc((100% / 5) - 30px);
        padding: 20px;
        margin: 15px;
        background-color: $grey;

        img {
            margin-bottom: 15px;
            object-fit: cover;
            object-position: top;
        }

        h4 {
            margin-bottom: 15px;
        }
    }
</style>