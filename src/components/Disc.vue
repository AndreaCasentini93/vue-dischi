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
        width: calc((100% / 5) - 40px);
        padding: 20px;
        margin: 15px 20px;
        background-color: $dark-grey;
        transition: transform .3s;

        &:hover {
            transform: scale(1.05);
        }

        img {
            display: block;
            width: 100%;
            height: 160px;
            margin-bottom: 15px;
            object-fit: cover;
            object-position: top;
        }

        h4 {
            margin: 5px auto 15px auto;
            text-transform: uppercase;
            font-size: 18px;
            font-weight: 700;
            color: $white;
        }

        h6 {
            margin: 5px auto;
            font-size: 16px;
            color: $light-grey;
        }
    }
</style>