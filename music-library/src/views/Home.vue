<template>
<div>
  <div class="home">
    <img alt="Music logo" src="../assets/logo.png">
  </div>

  <div class="search">
    <form class="pure-form">
      <i class="fas fa-search"></i><input v-model="searchText" />
    </form>
  </div>
  <br/>
  <SongSelection :songs="songs" />
</div>
</template>

<script>
import SongSelection from '../components/SongSelection.vue'

export default {
  name: 'Home',
  components: {
    SongSelection
  },
  data() {
    return {
        searchText: '',
      }
  },
  computed: {
    songs() {
      return this.$root.$data.songs.filter(song => song.title.toLowerCase().search(this.searchText) >= 0);
    }
  }
}
</script>
