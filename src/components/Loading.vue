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

</style>