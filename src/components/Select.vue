<template>
    <select class="form-select" aria-label="Default select example">
        <option selected>Seleziona Genere</option>
        <option value="rock">Rock</option>
        <option value="pop">Pop</option>
        <option value="jazz">Jazz</option>
        <option value="metal">Metal</option>
    </select>
</template>

<script>
export default {
    name: 'Select'
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    @import '../style/mixins.scss';

    .form-select {
        display: inline-block;
        width: unset;
        cursor: pointer;
    }
</style>