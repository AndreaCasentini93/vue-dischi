<template>
    <section id="loading">
        <div class="text">{{ msg }}</div>
        <i class="fas fa-spinner"></i>
        <div class="text">Loading...</div>
    </section>
</template>

<script>
export default {
    name: 'Loading',
    props: {
        msg: String
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    #loading {
        display: flex;
        flex-direction: column;
        @include flex-centering;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        background-color: $blue;

        .text {
            margin: 10px 0;
            font-size: 40px;
            color: $green;
        }

        svg:not(:root).svg-inline--fa {
            font-size: 40px;
            color: $green;
            animation: rotation 1s infinite linear;
        }
        @keyframes rotation {
            from {
                transform: rotate(0deg);
            }
            to {
                transform: rotate(360deg);
            }
        }
    }
</style>