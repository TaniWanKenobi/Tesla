<script lang="ts">
	import mugshot from '$lib/images/mugshot.png';
	
	let isHovered = $state(false);
</script>

<svelte:head>
	<title>Nikola Tesla - Scientist Overview</title>
	<meta name="description" content="Nikola Tesla - Inventor, Electrical Engineer, and Visionary Scientist" />
</svelte:head>

<section class="hero">
	<h1>Nikola Tesla</h1>
	<p class="subtitle">Inventor • Electrical Engineer • Visionary</p>
</section>

<section class="overview">
	<div class="name-card card">
		<h2>Scientist Name</h2>
		<div class="name-breakdown">
			<div class="name-part">
				<span class="label">First Name</span>
				<span class="value">Nikola</span>
			</div>
			<div class="name-part">
				<span class="label">Middle Name</span>
				<span class="value">—</span>
			</div>
			<div class="name-part">
				<span class="label">Last Name</span>
				<span class="value">Tesla</span>
			</div>
		</div>
	</div>

	<div class="portrait-section">
		<h2>Portrait</h2>
		<div 
			class="portrait-container"
			role="img"
			aria-label="Nikola Tesla portrait"
			onmouseenter={() => isHovered = true}
			onmouseleave={() => isHovered = false}
		>
			<img 
				src={mugshot} 
				alt="Nikola Tesla - Formal Portrait" 
				class="portrait"
				class:hovered={isHovered}
			/>
			{#if isHovered}
				<div class="portrait-overlay">
					<p>Nikola Tesla (1856-1943)</p>
				</div>
			{/if}
		</div>
	</div>

	<div class="time-period card">
		<h2>Time Period</h2>
		<div class="timeline">
			<span class="year birth">1856</span>
			<div class="timeline-bar"></div>
			<span class="year death">1943</span>
		</div>
		<p class="lifespan">87 years of brilliance</p>
	</div>

	<div class="quote-section card">
		<h2>Famous Quote</h2>
		<blockquote>
			"If you want to find the secrets of the universe, think in terms of energy, frequency, and vibration."
		</blockquote>
		<p class="quote-author">— Nikola Tesla</p>
	</div>
</section>

<style>
	.hero {
		text-align: center;
		padding: 3rem 0;
	}

	.subtitle {
		font-size: 1.2rem;
		color: rgba(168, 85, 247, 0.9);
		letter-spacing: 0.2em;
	}

	.overview {
		display: grid;
		gap: 2rem;
	}

	.name-card .name-breakdown {
		display: flex;
		justify-content: space-around;
		flex-wrap: wrap;
		gap: 1rem;
		margin-top: 1rem;
	}

	.name-part {
		text-align: center;
		padding: 1rem;
		background: rgba(0, 212, 255, 0.1);
		border-radius: 8px;
		min-width: 100px;
	}

	.name-part .label {
		display: block;
		font-size: 0.8rem;
		color: rgba(240, 248, 255, 0.6);
		margin-bottom: 0.5rem;
	}

	.name-part .value {
		display: block;
		font-size: 1.3rem;
		font-weight: 600;
		color: #00d4ff;
	}

	.portrait-section {
		text-align: center;
	}

	.portrait-container {
		position: relative;
		display: inline-block;
		cursor: pointer;
	}

	.portrait {
		max-width: 300px;
		width: 100%;
		transition: all 0.5s ease;
	}

	.portrait.hovered {
		transform: scale(1.02);
		box-shadow: 0 0 50px rgba(0, 212, 255, 0.6);
	}

	.portrait-overlay {
		position: absolute;
		bottom: 0;
		left: 0;
		right: 0;
		background: linear-gradient(transparent, rgba(10, 10, 30, 0.9));
		padding: 2rem 1rem 1rem;
		border-radius: 0 0 12px 12px;
	}

	.portrait-overlay p {
		margin: 0;
		color: #00d4ff;
		font-weight: 600;
	}

	.timeline {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 1rem;
		margin: 1.5rem 0;
	}

	.year {
		font-size: 1.5rem;
		font-weight: 700;
	}

	.birth {
		color: #00d4ff;
	}

	.death {
		color: #a855f7;
	}

	.timeline-bar {
		flex: 1;
		max-width: 200px;
		height: 4px;
		background: linear-gradient(90deg, #00d4ff, #a855f7);
		border-radius: 2px;
		position: relative;
	}

	.timeline-bar::before {
		content: '';
		position: absolute;
		top: 50%;
		left: 0;
		right: 0;
		height: 4px;
		background: linear-gradient(90deg, #00d4ff, #a855f7);
		animation: electricFlow 2s infinite linear;
	}

	@keyframes electricFlow {
		0% { opacity: 1; }
		50% { opacity: 0.5; }
		100% { opacity: 1; }
	}

	.lifespan {
		text-align: center;
		color: rgba(240, 248, 255, 0.7);
		font-style: italic;
	}

	.quote-section blockquote {
		font-size: 1.3rem;
	}

	.quote-author {
		text-align: right;
		color: #a855f7;
		font-weight: 600;
	}

	@media (min-width: 768px) {
		.overview {
			grid-template-columns: repeat(2, 1fr);
		}

		.portrait-section {
			grid-column: span 2;
		}

		.quote-section {
			grid-column: span 2;
		}
	}
</style>
