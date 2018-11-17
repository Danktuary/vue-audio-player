<template>
	<div id="app">
		<vue-audio />
	</div>
</template>

<script>
import VueAudio from './components/VueAudio.vue';

export default {
	name: 'App',

	components: {
		VueAudio,
	},
};
</script>

<style>
body {
	background-color: #2A2A2A;
}
</style>
