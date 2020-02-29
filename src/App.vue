<template>
	<div id="app">
		<Generate></Generate>
	</div>
</template>

<script>
import Generate from '@/components/Generate.vue'
export default {
	name: 'app',
	components: {
		Generate
	}
}
</script>

<style lang="scss">
#app {
	font-family: 'Quicksand', sans-serif;
}
</style>
