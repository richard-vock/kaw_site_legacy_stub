<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/svelte-logo.svg';
	import github from '$lib/images/github.svg';

	import MainMenu from './MainMenu.svelte';

	let y = 0;
	let vh = 0;
	$:home = $page.url.pathname === '/';
	$:threshold = home ? (parseInt(vh) - 40) : 0;
	$:sticky = y > threshold;

	let mobile = false;
	let sticky = false;
	let showLoginMenu = false;
</script>

<svelte:window bind:scrollY={y} bind:innerHeight={vh} />

<header class:mobile class:sticky class:nav={!mobile} class:login-mode={showLoginMenu}>
	<MainMenu />
</header>

<style>
	header {
        position: absolute;
        top: 0;
        left: 0;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: var(--menu-height);

        box-shadow: rgba(41, 44, 61, 0.1) 2px 15px 50px 0px;
        z-index: 980;
        background: white;
	}
	@media only screen and (min-width: 768px) {
		header {
			box-shadow: none;
			z-index: 0;
			background: none;
		}
	}

	header.sticky {
			position: fixed;
			top: 0;
			left: 0;
			box-shadow: rgba(41, 44, 61, 0.1) 2px 15px 50px 0px;
			z-index: 980;
			background: white;
	}

	.corner {
		width: 3em;
		height: 3em;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner img {
		width: 2em;
		height: 2em;
		object-fit: contain;
	}

	nav {
		display: flex;
		justify-content: center;
		--background: rgba(255, 255, 255, 0.7);
	}

	svg {
		width: 2em;
		height: 3em;
		display: block;
	}

	path {
		fill: var(--background);
	}

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		color: var(--color-text);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: var(--color-theme-1);
	}
</style>
