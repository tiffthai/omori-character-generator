<template>
	<CharGenerator />
	<!-- <img src="@/assets/OmoriBackgroundPink.jpg" /> -->
</template>

<script>
import CharGenerator from './components/CharGenerator.vue'

export default {
	name: 'App',
	components: {
		CharGenerator
	}
}
</script>

<style>
body, html {
	width: 100%;
	height: 100%;
	margin: 0;
	font-family: 'Schoolbell', cursive;
	letter-spacing: .1em;
}

#app {
	width: 100%;
	height: 100%;
	display: flex;
	font-family: 'Schoolbell', cursive;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	background-image: url("./assets/OmoriBackgroundPink.jpg");
	background-attachment: fixed;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: right;
}
</style>
