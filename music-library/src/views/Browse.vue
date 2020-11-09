<template>
<div>
	<div class="pure-menu">
		<h1>Filter by Artist</h1>
		<div class="pure-menu-list">
			<div class="pure-menu-item"><a @click="select('Panic! At The Disco')" href="#" class="pure-menu-link">Panic! At The Disco</a></div>
			<div class="pure-menu-item"><a @click="select('fun.')" href="#" class="pure-menu-link">fun.</a></div>
			<div class="pure-menu-item"><a @click="select('The Script')" href="#" class="pure-menu-link">The Script</a></div>
			<div class="pure-menu-item"><a @click="select('Maroon 5')" href="#" class="pure-menu-link">Maroon 5</a></div>
		</div>
	</div>
	<SongSelection :songs="songs" />
</div>
</template>


<script>
import SongSelection from "../components/SongSelection.vue"
export default {
	name: 'Browse',
	components: {
		SongSelection
	},
	data() {
		return {
			artist: '',
		}
	},
	computed: {
		songs() {
			return this.$root.$data.songs.filter(song => song.artist === this.artist);
		}
	},
	methods: {
		select(artist) {
			this.artist = artist;
		}
	}
}
</script>

<style scoped>
.pure-menu {
	margin-top: 75px;
}

.pure-menu-list {
	display: flex;
	flex-direction: row;
	justify-content: center;
}

.pure-menu-item {
	margin-top: 25px;
	margin-bottom: 50px;
	margin-right: 50px;
	margin-left: 50px;
	font-size: 25px;
}

</style>
