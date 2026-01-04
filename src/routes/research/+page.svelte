<script lang="ts">
	const locations = [
		{
			name: 'New York City',
			country: 'United States',
			description: 'Primary location for most of Tesla\'s revolutionary work. He operated multiple laboratories in Manhattan, including his famous lab on Houston Street.',
			highlights: ['AC motor development', 'Radio experiments', 'X-ray research']
		},
		{
			name: 'Colorado Springs',
			country: 'Colorado, USA',
			description: 'Site of Tesla\'s high-voltage electrical experiments in 1899. Here he built the largest Tesla coil ever constructed and claimed to have received signals from outer space.',
			highlights: ['High-voltage experiments', 'Wireless transmission tests', 'Artificial lightning']
		}
	];

	const facilities = [
		'Private laboratories',
		'Industrial research facilities',
		'Experimental power stations',
		'Wardenclyffe Tower (Long Island)'
	];

	let activeLocation = $state(0);
</script>

<svelte:head>
	<title>Research Locations - Nikola Tesla</title>
	<meta name="description" content="Where Tesla conducted his groundbreaking research" />
</svelte:head>

<section class="page-header">
	<h1>Research & Work Locations</h1>
	<p class="page-subtitle">Where innovation happened</p>
</section>

<section class="content">
	<div class="locations-section">
		<h2>Location of Research and Work</h2>
		<p>Nikola Tesla conducted most of his scientific research in:</p>

		<div class="location-tabs">
			{#each locations as location, i}
				<button 
					class="tab-button"
					class:active={activeLocation === i}
					onclick={() => activeLocation = i}
				>
					📍 {location.name}
				</button>
			{/each}
		</div>

		<div class="location-detail card">
			<h3>{locations[activeLocation].name}, {locations[activeLocation].country}</h3>
			<p>{locations[activeLocation].description}</p>
			<div class="highlights">
				<h4>Key Work:</h4>
				<ul>
					{#each locations[activeLocation].highlights as highlight}
						<li>{highlight}</li>
					{/each}
				</ul>
			</div>
		</div>
	</div>

	<div class="facilities-section card">
		<h2>Research Facilities</h2>
		<p>Tesla's work environments included:</p>
		<div class="facilities-grid">
			{#each facilities as facility}
				<div class="facility-item">
					<span class="facility-icon">🏛️</span>
					<span class="facility-name">{facility}</span>
				</div>
			{/each}
		</div>
	</div>

	<div class="map-placeholder card">
		<h2>Tesla's Journey</h2>
		<div class="journey-visual">
			<div class="journey-point">
				<span class="point-marker">1</span>
				<span class="point-label">Smiljan, Croatia</span>
				<span class="point-year">Born 1856</span>
			</div>
			<div class="journey-line"></div>
			<div class="journey-point">
				<span class="point-marker">2</span>
				<span class="point-label">Graz & Prague</span>
				<span class="point-year">Education</span>
			</div>
			<div class="journey-line"></div>
			<div class="journey-point">
				<span class="point-marker">3</span>
				<span class="point-label">Paris & Budapest</span>
				<span class="point-year">Early Career</span>
			</div>
			<div class="journey-line"></div>
			<div class="journey-point">
				<span class="point-marker">4</span>
				<span class="point-label">New York City</span>
				<span class="point-year">1884-1943</span>
			</div>
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

	.location-tabs {
		display: flex;
		gap: 1rem;
		margin: 1rem 0;
		flex-wrap: wrap;
	}

	.tab-button {
		background: rgba(255, 255, 255, 0.05);
		border: 1px solid rgba(0, 212, 255, 0.3);
		color: rgba(240, 248, 255, 0.8);
		padding: 0.75rem 1.5rem;
		border-radius: 8px;
		cursor: pointer;
		transition: all 0.3s ease;
		font-weight: 500;
	}

	.tab-button:hover {
		border-color: #00d4ff;
		background: rgba(0, 212, 255, 0.1);
	}

	.tab-button.active {
		background: linear-gradient(90deg, #00d4ff, #a855f7);
		color: white;
		border-color: transparent;
	}

	.location-detail {
		animation: fadeIn 0.3s ease;
	}

	.location-detail h3 {
		color: #00d4ff;
		margin-top: 0;
	}

	@keyframes fadeIn {
		from { opacity: 0; transform: translateY(10px); }
		to { opacity: 1; transform: translateY(0); }
	}

	.highlights h4 {
		color: #a855f7;
		margin-bottom: 0.5rem;
	}

	.facilities-grid {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.facility-item {
		display: flex;
		align-items: center;
		gap: 1rem;
		padding: 1rem;
		background: rgba(0, 212, 255, 0.1);
		border-radius: 8px;
		transition: all 0.3s ease;
	}

	.facility-item:hover {
		transform: translateX(10px);
		background: rgba(168, 85, 247, 0.1);
	}

	.facility-icon {
		font-size: 1.5rem;
	}

	.facility-name {
		font-weight: 500;
		color: rgba(240, 248, 255, 0.9);
	}

	.journey-visual {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 0;
		padding: 2rem 0;
	}

	.journey-point {
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
		padding: 1rem;
	}

	.point-marker {
		width: 40px;
		height: 40px;
		background: linear-gradient(135deg, #00d4ff, #a855f7);
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		font-weight: 700;
		color: white;
		margin-bottom: 0.5rem;
	}

	.point-label {
		font-weight: 600;
		color: #00d4ff;
	}

	.point-year {
		font-size: 0.85rem;
		color: rgba(240, 248, 255, 0.6);
	}

	.journey-line {
		width: 4px;
		height: 30px;
		background: linear-gradient(180deg, #00d4ff, #a855f7);
	}

	@media (min-width: 768px) {
		.facilities-grid {
			grid-template-columns: repeat(2, 1fr);
		}

		.journey-visual {
			flex-direction: row;
			justify-content: center;
		}

		.journey-line {
			width: 50px;
			height: 4px;
		}
	}
</style>
