<script lang="ts">
	import { resolve } from '$app/paths';
</script>

<svelte:head>
	<title>About - Nikola Tesla</title>
	<meta name="description" content="About this Nikola Tesla tribute site" />
</svelte:head>

<section class="page-header">
	<h1>About This Site</h1>
</section>

<section class="content">
	<div class="card">
		<p>
			This site is a tribute to <strong>Nikola Tesla</strong> (1856-1943), one of history's 
			greatest inventors and scientists. His contributions to electrical engineering and 
			physical chemistry continue to power our modern world.
		</p>
		<p>
			<a href={resolve('/')}>Return to Home →</a>
		</p>
	</div>
</section>

<style>
	.page-header {
		text-align: center;
		padding: 2rem 0;
	}

	.content {
		max-width: 600px;
		margin: 0 auto;
	}
</style>
