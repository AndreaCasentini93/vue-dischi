<template>
    <div class="text-center">
        <img :src="card.poster" :alt="card.title">
        <h4>{{ card.title }}</h4>
        <h6>{{ card.author }}<br>{{ card.year }}</h6>
    </div>
</template>

<script>
export default {
    name: 'Disc',
    props: {
        card: Object
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    div {
        width: calc((100% / 5) - 36px);
        padding: 10px;
        margin: 12px 18px;
        background-color: $dark-grey;

        img {
            display: block;
            width: 100%;
            height: 180px;
            margin-bottom: 15px;
            object-fit: cover;
            object-position: top;
        }

        h4 {
            margin: 5px auto 15px auto;
            text-transform: uppercase;
            font-size: 21px;
            font-weight: 700;
            color: $white;
        }

        h6 {
            margin: 5px auto;
            font-size: 18px;
            color: $light-grey;
        }
    }
</style>