<script>
	import Header from './Header.svelte';
	import HomeBanner from './HomeBanner.svelte';
	import './styles.css';
</script>

<div class="app">
	<Header />

	<main>
		<slot />
	</main>

</div>

<style>
.app {
	display: flex;
	flex-direction: column;
	min-height: 100vh;
}
main {
	width: 100%;
	/* padding-top: 200px; */
}

</style>
