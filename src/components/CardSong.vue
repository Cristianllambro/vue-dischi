<template>
  <div class="card-song col-6 col-md-4 col-lg-3 mb-4 text-center d-flex justify-content-center">
        <div class=" help pb-5">
            <img class="img-fluid pt-4" :src="sonList.poster" :alt="sonList.author">
            <h2 class="text-white text-uppercase fs-4">{{ songList.title }}</h2>
            <p class="fs-5 text-secondary">{{ songList.author }}</p>
            <p class="fs-6 text-secondary">{{ songList.year }}</p>
        </div>
  </div>
</template>

<script>
export default {
    name: 'CardSong',
    props: {
        songList: Object,
    }
}
</script>

<style lang="scss" scoped>
.help{
    width: 200px;
    background-color: #2e3a46;
}

img{
    width: 170px;
}

p{
    margin: 0;
}
</style>