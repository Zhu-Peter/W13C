<template>
    <div id="list_container">
        <div v-for="song in songs" v-bind:key="song.song_id" @click="chooseSong(song.song_id)">
            <div class="song_container" ref="song" @mouseover="songBackground(song.song_id)">
                <span class="id">
                    {{ song.song_id }}
                </span>
                <span class="title">
                    {{ song.title }}
                </span>
                <span class="artist">
                    {{ song.artist }}
                </span>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "SongDatabase",
    props: {
        currentSong: Number
    },
    data() {
        return {
            songs: [
                {
                    title: `song a`,
                    artist: `artist a`,
                    song_id: 1,
                    image_url: "https://www.reshot.com/preview-assets/illustrations/RVNQBFTSA5/vynil-app-player-RVNQBFTSA5-w1600.jpg"
                }, {
                    title: `song b`,
                    artist: `artist b`,
                    song_id: 2,
                    image_url: "@/assets/logo.png"
                }, {
                    title: `song c`,
                    artist: `artist c`,
                    song_id: 3,
                    image_url: "@/assets/logo.png"
                }, {
                    title: `song d`,
                    artist: `artist d`,
                    song_id: 4,
                    image_url: "@/assets/logo.png"
                }, {
                    title: `song e`,
                    artist: `artist e`,
                    song_id: 5,
                    image_url: "@/assets/logo.png"
                },
                {
                    title: `song f`,
                    artist: `artist f`,
                    song_id: 6,
                    image_url: "@/assets/logo.png"
                }, {
                    title: `song g`,
                    artist: `artist g`,
                    song_id: 7,
                    image_url: "@/assets/logo.png"
                }, {
                    title: `song h`,
                    artist: `artist h`,
                    song_id: 8,
                    image_url: "@/assets/logo.png"
                }, {
                    title: `song i`,
                    artist: `artist i`,
                    song_id: 9,
                    image_url: "@/assets/logo.png"
                }, {
                    title: `song j`,
                    artist: `artist j`,
                    song_id: 10,
                    image_url: "@/assets/logo.png"
                },
            ]
        }
    },
    methods: {
        chooseSong: function(song){
            this.$emit(`chooseSong`, this.songs[song-1])
        },
        songBackground: function(song){
            // console.log(this.$refs.song[song-1])
            this.$refs.song[song-1].style.backgroundColor = "lightgray"
            for(let i=0; i<this.$refs.song.length;i++){
                if(!(i == song-1)){
                    this.$refs.song[i].style.backgroundColor = "white"
                }
            }
        }
    },
    mounted() {
        // this.songBackground();
    },
}
</script>
<style>
*{
    box-sizing: border-box;
}
#list_container{
    border: 1px black solid;
    height: 260px;
    overflow: auto;
    scrollbar-color: transparent transparent;
    scrollbar-width: 0px;
}
.song_container{
    padding-top: 15px;
    margin-top: 5px;
    cursor: pointer;
}
.title{
    margin-left: 30px;
    font-weight: bolder;
}
.artist{
    margin-left: 15px;
    color: darkgray;
    font-style: italic;
}
</style>