<template>
<div class="wrapper">
	<div v-if="playlistSize == 0">
		<p>Playlist is empty</p>
	</div>

	<div v-if="playlistSize > 0" class="playlistItems">
		<h3>Your Playlist</h3>
		<div class="playlistItem" v-for="playlistItem in playlistItems" :key="playlistItem.id">
			<div class="image">
				<img :src="'/images/songs/'+playlistItem.image">
			</div>
			<div class="info">
				<div class="title">
					<h1>{{playlistItem.title}}</h1>
				</div>
				<div class="duration">
					<h2>{{playlistItem.artist}}</h2>
				</div>
			</div>
			<div class="removeButton">
				<button class="auto" ><a @click="removeFromPlaylist(playlistItem.indexOf)">Remove from Playlist</a></button>
			</div>

		</div>
	</div>
</div>
</template>


<script>

export default {
	name: "PlaylistList",
	computed: {
		playlistItems() {
			return this.$root.$data.playlist;
		},
		playlistSize() {
			return this.$root.$data.playlist.length;
		}
	},
	methods: {
		removeFromPlaylist(indexOfSongToRemove) {
			this.$root.$data.playlist.splice(indexOfSongToRemove, 1);
		},
	}

}
</script>


<style scoped>

.playlistItems {
	display: flex;
	flex-direction: column;
	align-items: left;
}

.playlistItem {
	display: flex;
	align-items: center;
	margin: 15px;
}

.info {
	margin-left: 100px;
	margin-right: 100px;
	display: flex;
	flex-direction: column;
}

.removeButton {
	align-items: center;
	max-height: 50px;
}

h1, h2 {
	margin: 5px;
}

h2 {
	font-size: 16px;
}

h3 {
	font-size: 50px;
	margin: 25px;
	text-align: left;
}


</style>
