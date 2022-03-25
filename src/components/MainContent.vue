<template>
    <main>
        <div class="container">

            <!-- animazione carimaneto -->
            <div class="charge" v-if="arrAlbumSong == null">
                <div id="preloader_1">
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </div>

            <!-- elemento colonna card -->
            <div v-else class="row row-cols-lg-5 pt-5">
                <card-song v-for="element in searchAlbum" :key="element.title" 
                :poster = element.poster
                :title = element.title
                :author = element.author
                :year = element.year /> 
                
            </div>
        </div>
    </main>
</template>

<script>
import CardSong from './CardSong.vue'
const axios = require('axios');

export default {
    name: 'MainContent',
    data () {
        return {
            // success: true,
            arrAlbumSong: null,
            // [
            //     {
            //         poster: "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg",
            //         title: "New Jersey",
            //         author: "Bon Jovi",
            //         genre: "Rock",
            //         year: "1988"
            //     },
            //     {
            //         poster: "https://img.discogs.com/vknPDdrqRbT92pNRX0W4I5N91jg=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-1246953-1448927086-6590.jpeg.jpg",
            //         title: "Live at Wembley 86",
            //         author: "Queen",
            //         genre: "Pop",
            //         year: "1992"
            //     },
            //     {
            //         poster: "https://images-na.ssl-images-amazon.com/images/I/41JD3CW65HL.jpg",
            //         title: "Ten's Summoner's Tales",
            //         author: "Sting",
            //         genre: "Pop",
            //         year: "1993"
            //     },
            //     {
            //         poster: "https://cdn2.jazztimes.com/2018/05/SteveGadd-800x723.jpg",
            //         title: "Steve Gadd Band",
            //         author: "Steve Gadd Band",
            //         genre: "Jazz",
            //         year: "2018"
            //     },
            //     {
            //         poster: "https://images-na.ssl-images-amazon.com/images/I/810nSIQOLiL._SY355_.jpg",
            //         title: "Brave new World",
            //         author: "Iron Maiden",
            //         genre: "Metal",
            //         year: "2000"
            //     },
            //     {
            //         poster: "https://upload.wikimedia.org/wikipedia/en/9/97/Eric_Clapton_OMCOMR.jpg",
            //         title: "One more car, one more raider",
            //         author: "Eric Clapton",
            //         genre: "Rock",
            //         year: "2002"
            //     },
            //     {
            //         poster: "https://images-na.ssl-images-amazon.com/images/I/51rggtPgmRL.jpg",
            //         title: "Made in Japan",
            //         author: "Deep Purple",
            //         genre: "Rock",
            //         year: "1972"
            //     },
            //     {
            //         poster: "https://images-na.ssl-images-amazon.com/images/I/81r3FVfNG3L._SY355_.jpg",
            //         title: "And Justice for All",
            //         author: "Metallica",
            //         genre: "Metal",
            //         year: "1988"
            //     },
            //     {
            //         poster: "https://img.discogs.com/KOBsqQwKiNKH-q927oHMyVdDzSo=/fit-in/596x596/filters:strip_icc():format(jpeg):mode_rgb():quality(90)/discogs-images/R-6406665-1418464475-6120.jpeg.jpg",
            //         title: "Hard Wired",
            //         author: "Dave Weckl",
            //         genre: "Jazz",
            //         year: "1994"
            //     },
            //     {
            //         poster: "https://m.media-amazon.com/images/I/71K9CbNZPsL._SS500_.jpg",
            //         title: "Bad",
            //         author: "Michael Jacjson",
            //         genre: "Pop",
            //         year: "1987"
            //     }
            // ],
        };
    },

    created () {
        setTimeout (() => {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
                .then((response) => {
                    this.arrAlbumSong = response.data.response;
                });
        }, 1000)
    },
    computed: {
        searchAlbum () {
          return this.arrAlbumSong.filter((ele) => ele.genre.includes(this.modSearch))
        },
    },

    components: {
        CardSong,
    },

    props: {
        modSearch: String,
    }
}
</script>

<style lang="scss" scoped>
main{
    background-color: #1e2d3b;
}

.charge{
    height: calc(100vh - 70px);
    display: flex;
    align-items: center;
    justify-content: center;
}

// caricamento animazione
#preloader_1{
    position:relative;
}
#preloader_1 span{
    display:block;
    bottom:0px;
    width: 9px;
    height: 5px;
    background:#9b59b6;
    position:absolute;
    animation: preloader_1 1.5s  infinite ease-in-out;
}
 
#preloader_1 span:nth-child(2){
left:11px;
animation-delay: .2s;
 
}
#preloader_1 span:nth-child(3){
left:22px;
animation-delay: .4s;
}
#preloader_1 span:nth-child(4){
left:33px;
animation-delay: .6s;
}
#preloader_1 span:nth-child(5){
left:44px;
animation-delay: .8s;
}
@keyframes preloader_1 {
    0% {height:5px;transform:translateY(0px);background:#9b59b6;}
    25% {height:30px;transform:translateY(15px);background:#3498db;}
    50% {height:5px;transform:translateY(0px);background:#9b59b6;}
    100% {height:5px;transform:translateY(0px);background:#9b59b6;}
}

</style>