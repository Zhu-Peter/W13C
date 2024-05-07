<template lang="">
    <div>
        <h1>Now Playing</h1>
        <SongPlaylist/>
    </div>
</template>
<script>
import SongPlaylist from "./SongPlaylist.vue"
export default {
    name: 'NowPlaying',
  components: {
    SongPlaylist
  }
}
</script>
<style lang="">
    
</style>