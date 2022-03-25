<template>
    <div class="header bg-secondary bg-gradient d-flex justify-content-between align-items-center">
        <div class="logo ps-3">
            ICONA
        </div>
        <div class="select-fix pe-3">
            <select class="form-select" aria-label="Default select example" v-model="selectGenere" @change="$emit('genSearch', selectGenere)">
                <option value="">Tutti i Generi</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HeaderContent',
    data () {
        return {
            selectGenere: '',
        }
    }
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
