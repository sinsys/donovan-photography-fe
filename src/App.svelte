<script lang="ts">
	import Router from 'svelte-spa-router'
	import Header from './layout/Header.svelte'
	import Home from './routes/Home.svelte'
	import Photos from './routes/Photos.svelte'
	import SinglePhoto from './routes/SinglePhoto.svelte'
	import Quote from './routes/Quote.svelte'
	import About from './routes/About.svelte'
	import Portfolio from './routes/Portfolio.svelte'
	import NotFound from './routes/NotFound.svelte'

	const routes = {
		// Unauthenticated Routes
		'/': Home,
		'/quote': Quote,
		'/about': About,
		'/portfolio': Portfolio,

		// Authenticated Routes
		'/photos/:id?': Photos,
		'/photos/:id/:photoId': SinglePhoto,

		// Unknown
		'*': NotFound
	}
</script>

<main>
	<div class="header">
		<Header />
	</div>
	<div class="router">
		<Router {routes} />
	</div>
</main>

<style lang="scss">
	@import './styles/common.scss';

	main {
		background: $colorDark;
		background: url('../images/stock-city.jpg') no-repeat center center fixed;
		-webkit-background-size: cover;
		background-size: cover;
		
		margin: 0 auto;
		display: flex;
		justify-content: flex-start;
		align-items: center;
		min-height: 100vh;
		min-width: 100vw;
		overflow: hidden;
		flex-direction: column;

		.header, .router {
			min-width: 100%;
			display: flex;
			margin: 0;
			padding: 0;
		}

		.header {
			flex-shrink: 1;
			background: $colorDark;
		}

		.router {
			flex-grow: 1;
			min-height: 100%;
			min-width: 100%;
		}
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>