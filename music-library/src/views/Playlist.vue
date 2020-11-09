<template>
<div>
	<PlaylistList :playlistItems="playlistItems" />
</div>
</template>


<script>
import PlaylistList from "../components/PlaylistList.vue"
export default {
	name: 'Playlist',
	components: {
		PlaylistList
	},
	computed: {
		playlistItems() {
			return this.$root.$data.playlist;
		}
	}
}
</script>
