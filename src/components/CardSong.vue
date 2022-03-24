<template>
  <div class="card-song col-6 col-md-4 col-lg mb-4 text-center d-flex justify-content-center">
        <div class=" help pb-5">
            <img class="img-fluid pt-4" :src="poster" :alt="author">
            <h2 class="text-white text-uppercase fs-4 pt-3">{{ title }}</h2>
            <p class="fs-5 text-secondary">{{ author }}</p>
            <p class="fs-6 text-secondary">{{ year }}</p>
        </div>
  </div>
</template>

<script>
export default {
    name: 'CardSong',
    props: {
        author: String,
        year: String,
        title: String,
        poster: String,
    }
}
</script>

<style lang="scss" scoped>
.help{
    width: 220px;
    background-color: #2e3a46;
}

img{
    width: 170px;
}

p{
    margin: 0;
}

</style>