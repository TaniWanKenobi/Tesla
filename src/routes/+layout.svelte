<script lang="ts">
	import Header from './Header.svelte';
	import './layout.css';

	let { children } = $props();
</script>

<div class="app">
	<Header />
	<main>{@render children()}</main>
	<footer>
		<div class="footer-content">
			<p class="copyright">Nikola Tesla Tribute &copy; 2026</p>
			<p class="tagline">"The present is theirs; the future, for which I really worked, is mine."</p>
		</div>
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 2rem 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		background: rgba(10, 10, 30, 0.9);
		border-top: 1px solid rgba(168, 85, 247, 0.3);
		padding: 2rem 1rem;
		text-align: center;
	}

	.footer-content {
		max-width: 64rem;
		margin: 0 auto;
	}

	.copyright {
		color: rgba(240, 248, 255, 0.6);
		font-size: 0.9rem;
		margin: 0;
	}

	.tagline {
		color: rgba(168, 85, 247, 0.8);
		font-style: italic;
		font-size: 0.85rem;
		margin: 0.5rem 0 0 0;
	}

	@media (min-width: 480px) {
		main {
			padding: 2rem;
		}
	}
</style>
