<template>
    <a :href="card.poster" class="text-center">
        <img :src="card.poster" :alt="card.title">
        <h4>{{ card.title }}</h4>
        <h6>{{ card.author }}<br>{{ card.year }}</h6>
    </a>
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

    a {
        width: calc((100% / 5) - 30px);
        padding: 12px;
        margin: 10px 15px;
        background-color: $dark-grey;
        transition: transform .3s;

        &:hover {
            transform: scale(1.05);
        }

        img {
            display: block;
            width: 100%;
            margin-bottom: 15px;
            object-fit: cover;
            object-position: top;
        }

        h4 {
            line-height: 1.5;
            margin: 5px auto 15px auto;
            text-transform: uppercase;
            font-size: 14px;
            font-weight: 700;
            color: $white;
        }

        h6 {
            line-height: 1.3;
            margin: 5px auto 10px auto;
            font-size: 14px;
            color: $light-grey;
        }
    }
</style>