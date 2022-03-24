<template>
    <div class="header bg-secondary bg-gradient d-flex justify-content-between align-items-center">
        <p class="ps-3 text-uppercase">icona</p>
        <div class="select-fix pe-3">
            <select class="form-select" aria-label="Default select example">
                <option selected>Seleziona Genere</option>
                <option value="1">Rock</option>
                <option value="2">Pop</option>
                <option value="3">Jazz</option>
                <option value="3">Metal</option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HeaderContent',
}
</script>

<style lang="scss" scoped>

.header{
    width: 100%;
    height: 70px;

    .form-select{
        width: 200px;
    }
}
</style>
