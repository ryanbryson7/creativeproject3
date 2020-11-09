<template>
<div class="song-grid">
	<div class="songs">
		<div class="song" v-for="song in songs" :key="song.id">
			<div class="image">
				<img :src="'/images/songs/'+song.image">
			</div>
			<div class="song-info">
				<h1>{{song.title}}</h1>
				<h2>{{song.artist}}</h2>
				<p>({{song.duration}})</p>
				<button class="auto" ><a @click="addToPlaylist(song)">+ Add to Playlist</a></button>
			</div>
		</div>
	</div>
</div>
</template>


<script>
export default {
	name: 'SongSelection',
	props: {
		songs: Array,
	},
	methods: {
		addToPlaylist(songToAdd) {
			this.$root.$data.playlist.push(songToAdd);
		}
	}
}
</script>


<style scoped>
.song-grid {
	display: flex;
	align-items: center;
	justify-content: center;
}

.songs {
	display: flex;
	flex-wrap: wrap;
	justify-content: space-around;
}

.song {
	margin: 10px;
	display: flex;
	flex-direction: row;
}

.image {
	margin: 10px;
}

h1 {
	margin-bottom: 0px;
}

h2, duration, p {
	margin: 0px;
}

p {
	font-size: 14px;
}

h2 {
	font-size: 18px;
	margin-bottom: 25px;
}


</style>
