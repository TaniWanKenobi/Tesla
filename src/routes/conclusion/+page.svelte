<script lang="ts">
	import { resolve } from '$app/paths';

	const chemistryConnections = [
		'Physical chemistry understanding',
		'Electrochemistry advancements',
		'Chemical experimentation enablement',
		'Industrial chemical production',
		'Modern scientific research methods'
	];

	let highlightIndex = $state(0);

	$effect(() => {
		const interval = setInterval(() => {
			highlightIndex = (highlightIndex + 1) % chemistryConnections.length;
		}, 2000);
		return () => clearInterval(interval);
	});
</script>

<svelte:head>
	<title>Conclusion - Nikola Tesla</title>
	<meta name="description" content="Why Nikola Tesla is significant to chemistry and science" />
</svelte:head>

<section class="page-header">
	<h1>Conclusion</h1>
	<p class="page-subtitle">Tesla's lasting legacy in science</p>
</section>

<section class="content">
	<div class="main-conclusion card">
		<h2>Why Nikola Tesla Is a Famous Scientist</h2>
		<p>
			Although Tesla is best known as an <strong>engineer</strong>, his work deeply 
			influenced <strong>chemistry</strong>, especially <strong>physical chemistry</strong> 
			and <strong>electrochemistry</strong>.
		</p>
		<p>
			His discoveries about electrical energy and matter enabled:
		</p>
		<ul class="chemistry-list">
			{#each chemistryConnections as connection, i}
				<li class:highlight={highlightIndex === i}>{connection}</li>
			{/each}
		</ul>
		<p>
			Tesla's contributions changed how energy is used in chemistry and everyday life. 
			Without his innovations, modern laboratories, pharmaceutical manufacturing, and 
			materials science would not be possible.
		</p>
	</div>

	<div class="legacy-section">
		<h2>Tesla's Enduring Legacy</h2>
		<div class="legacy-grid">
			<div class="legacy-card card">
				<span class="legacy-icon">⚡</span>
				<h3>Power Infrastructure</h3>
				<p>Every electrical outlet in your home uses Tesla's AC system</p>
			</div>
			<div class="legacy-card card">
				<span class="legacy-icon">🔬</span>
				<h3>Scientific Method</h3>
				<p>His experimental approach influenced generations of scientists</p>
			</div>
			<div class="legacy-card card">
				<span class="legacy-icon">🌍</span>
				<h3>Global Impact</h3>
				<p>Billions of people benefit from his inventions daily</p>
			</div>
			<div class="legacy-card card">
				<span class="legacy-icon">🚗</span>
				<h3>Modern Inspiration</h3>
				<p>Companies like Tesla Inc. carry his name and vision forward</p>
			</div>
		</div>
	</div>

	<div class="final-quote card">
		<blockquote>
			"The day science begins to study non-physical phenomena, it will make more progress 
			in one decade than in all the previous centuries of its existence."
		</blockquote>
		<p class="quote-author">— Nikola Tesla</p>
	</div>

	<div class="navigation-cards">
		<h2>Explore More</h2>
		<div class="nav-grid">
			<a href={resolve('/')} class="nav-card">
				<span class="nav-icon">🏠</span>
				<span class="nav-label">Home</span>
			</a>
			<a href={resolve('/early-life')} class="nav-card">
				<span class="nav-icon">👶</span>
				<span class="nav-label">Early Life</span>
			</a>
			<a href={resolve('/accomplishments')} class="nav-card">
				<span class="nav-icon">🏆</span>
				<span class="nav-label">Accomplishments</span>
			</a>
			<a href={resolve('/facts')} class="nav-card">
				<span class="nav-icon">💡</span>
				<span class="nav-label">Fun Facts</span>
			</a>
		</div>
	</div>
</section>

<style>
	.page-header {
		text-align: center;
		padding: 2rem 0;
	}

	.page-subtitle {
		color: rgba(168, 85, 247, 0.9);
		font-size: 1.1rem;
	}

	.content {
		display: flex;
		flex-direction: column;
		gap: 2rem;
	}

	.main-conclusion {
		background: linear-gradient(135deg, rgba(0, 212, 255, 0.1), rgba(168, 85, 247, 0.1));
	}

	.chemistry-list {
		margin: 1rem 0;
	}

	.chemistry-list li {
		padding: 0.75rem 0.75rem 0.75rem 2rem;
		margin: 0.5rem 0;
		border-radius: 8px;
		transition: all 0.3s ease;
	}

	.chemistry-list li.highlight {
		background: rgba(0, 212, 255, 0.2);
		border-left: 3px solid #00d4ff;
	}

	.legacy-grid {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.legacy-card {
		text-align: center;
		transition: all 0.3s ease;
	}

	.legacy-card:hover {
		transform: translateY(-5px);
	}

	.legacy-icon {
		font-size: 2.5rem;
		display: block;
		margin-bottom: 0.5rem;
	}

	.legacy-card h3 {
		margin: 0.5rem 0;
		color: #00d4ff;
	}

	.legacy-card p {
		margin: 0;
		font-size: 0.9rem;
	}

	.final-quote {
		text-align: center;
		border: 2px solid rgba(168, 85, 247, 0.5);
	}

	.final-quote blockquote {
		font-size: 1.2rem;
		border: none;
		background: none;
		padding: 0;
		margin: 0;
	}

	.quote-author {
		color: #a855f7;
		font-weight: 600;
		margin-top: 1rem;
	}

	.navigation-cards h2 {
		text-align: center;
	}

	.nav-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 1rem;
		margin-top: 1rem;
	}

	.nav-card {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 1.5rem;
		background: rgba(255, 255, 255, 0.05);
		border: 1px solid rgba(0, 212, 255, 0.3);
		border-radius: 12px;
		text-decoration: none;
		transition: all 0.3s ease;
	}

	.nav-card:hover {
		border-color: #00d4ff;
		background: rgba(0, 212, 255, 0.1);
		transform: translateY(-5px);
		box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
	}

	.nav-icon {
		font-size: 2rem;
		margin-bottom: 0.5rem;
	}

	.nav-label {
		color: #00d4ff;
		font-weight: 600;
	}

	@media (min-width: 768px) {
		.legacy-grid {
			grid-template-columns: repeat(2, 1fr);
		}

		.nav-grid {
			grid-template-columns: repeat(4, 1fr);
		}
	}
</style>
