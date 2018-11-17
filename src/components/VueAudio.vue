<template>
	<div class="vue-audio-player-wrapper">
		<h1>Demo - Preview Song</h1>
		<img class="song-cover" src="../assets/images/logo.png" alt="" />
		<audio class="vue-audio-player" type="audio/mp3" controls></audio>
	</div>
</template>

<script>
import 'mediaelement';
// TODO: See if this is actually necessary later
import 'mediaelement/build/mediaelementplayer-legacy.min.css';

export default {
	name: 'VueAudio',

	mounted() {
		const player = this.$el.querySelector('.vue-audio-player');
		player.src = require('../assets/audio/counterattack.mp3');
		player.load();

		// eslint-disable-next-line no-undef
		new MediaElementPlayer(player, {
			tabindex: 0,
			alwaysShowControls: true,
			features: ['playpause', 'volume', 'progress', 'duration'],
			audioVolume: 'horizontal',
			audioWidth: 400,
			audioHeight: 120,
			classPrefix: 'mejs-',
		});
	},
};
</script>

<style lang="scss">
.vue-audio-player-wrapper {
	position: relative;
}

.vue-audio-player {
	display: inline-block;
	position: relative;
	width: 400px;
	height: 125px;
	color: #ececec;
	text-shadow: 1px 1px 1px rgba(0, 0, 0, 0.5);
	background: #4c4e5a;
	background: linear-gradient(to bottom, #4c4e5a 0%, #2c2d33 100%);
	border-radius: 3px;

	div, h1, a, img, span, button {
		margin: 0;
		padding: 0;
		border: none;
		outline: none;
	}

	h1 {
		position: absolute;
		top: 15px;
		left: 165px;
		font-family: Helvetica, Arial, sans-serif;
		font-weight: bold;
		font-size: 14px;
		transition: top 0.2s ease-in-out;
		max-width: 205px;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}

	.song-cover {
		position: absolute;
		top: 0;
		left: 0;
		height: 120px;
		width: 115px;
		border-radius: 3px 0 0 0;
	}
}

@import '../assets/scss/vue-audio-player/index.scss';
</style>
