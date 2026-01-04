<script lang="ts">
	const accomplishments = [
		{
			title: 'AC Power System',
			description: 'Made it possible to deliver electricity to homes, factories, and cities safely and efficiently',
			impact: 'Powers the entire modern world'
		},
		{
			title: 'Industrial Chemistry Advancement',
			description: 'Enabled the development of modern laboratories and chemical manufacturing processes',
			impact: 'Foundation for pharmaceutical and materials industry'
		},
		{
			title: 'Refrigeration Technology',
			description: 'AC motors made refrigeration practical for homes and industry',
			impact: 'Revolutionized food storage and medicine'
		},
		{
			title: 'Electric Lighting',
			description: 'AC power distribution made widespread electric lighting possible',
			impact: 'Extended productive hours for society'
		},
		{
			title: 'Radio Technology',
			description: 'Pioneered wireless transmission principles',
			impact: 'Enabled global communication'
		},
		{
			title: 'Electric Motors',
			description: 'Invented the AC induction motor, still used today',
			impact: 'Powers everything from fans to factories'
		}
	];

	const awards = [
		{ name: 'Edison Medal', year: '1917', description: 'Highest honor in electrical engineering' },
		{ name: 'Tesla (T)', year: 'Posthumous', description: 'SI unit of magnetic field strength named in his honor' }
	];

	let expandedAccomplishment = $state<number | null>(null);
</script>

<svelte:head>
	<title>Accomplishments - Nikola Tesla</title>
	<meta name="description" content="Tesla's revolutionary accomplishments and their global impact" />
</svelte:head>

<section class="page-header">
	<h1>Accomplishments & Global Impact</h1>
	<p class="page-subtitle">Innovations that shaped modern civilization</p>
</section>

<section class="content">
	<div class="intro card">
		<p>
			Nikola Tesla's accomplishments <strong>revolutionized the modern world</strong>. 
			His alternating current system made it possible to deliver electricity to homes, 
			factories, and cities safely and efficiently. This single innovation enabled 
			virtually every modern technology we depend on today. 
		</p>
		<p style="margin-top: 1.5rem;">
			By allowing power to travel long distances without major losses, Tesla’s system opened the door to widespread electrification, 
			which in turn fueled advances in communication, medicine, manufacturing, transportation, and everyday life.
			 Everything from lighting our homes to running hospitals and powering global industries traces back to the foundation he created, 
			 making his contribution one of the most transformative in human history.
		</p>
	</div>

	<div class="accomplishments-section">
		<h2>Major Accomplishments</h2>
		<div class="accomplishments-grid">
			{#each accomplishments as item, i}
				<button 
					class="accomplishment-card"
					class:expanded={expandedAccomplishment === i}
					onclick={() => expandedAccomplishment = expandedAccomplishment === i ? null : i}
				>
					<div class="accomplishment-header">
						<h3>{item.title}</h3>
						<span class="expand-icon">{expandedAccomplishment === i ? '−' : '+'}</span>
					</div>
					{#if expandedAccomplishment === i}
						<div class="accomplishment-details">
							<p>{item.description}</p>
							<div class="impact-badge">
								<span class="impact-label">Impact:</span>
								<span class="impact-text">{item.impact}</span>
							</div>
						</div>
					{/if}
				</button>
			{/each}
		</div>
	</div>

	<div class="benefits-section card">
		<h2>Benefits to Modern Society</h2>
		<div class="benefits-list">
			<div class="benefit-item">
				<span class="benefit-icon">🏥</span>
				<div class="benefit-content">
					<h4>Medical Equipment</h4>
					<p>MRI machines, X-rays, and electronic medical devices</p>
				</div>
			</div>
			<div class="benefit-item">
				<span class="benefit-icon">🔬</span>
				<div class="benefit-content">
					<h4>Scientific Research</h4>
					<p>Powers laboratories and research equipment worldwide</p>
				</div>
			</div>
			<div class="benefit-item">
				<span class="benefit-icon">🏭</span>
				<div class="benefit-content">
					<h4>Industrial Manufacturing</h4>
					<p>Factory automation and chemical production</p>
				</div>
			</div>
			<div class="benefit-item">
				<span class="benefit-icon">🌐</span>
				<div class="benefit-content">
					<h4>Power Grids</h4>
					<p>National and international electricity distribution</p>
				</div>
			</div>
		</div>
	</div>

	<div class="awards-section">
		<h2>Awards and Recognition</h2>
		<div class="awards-grid">
			{#each awards as award}
				<div class="award-card card">
					<div class="award-icon">🏆</div>
					<h3>{award.name}</h3>
					<span class="award-year">{award.year}</span>
					<p>{award.description}</p>
				</div>
			{/each}
		</div>
	</div>

	<div class="quote-box card">
		<blockquote>
			"The scientific man does not aim at an immediate result. He does not expect that 
			his advanced ideas will be readily taken up. His work is like that of the planter — 
			for the future."
		</blockquote>
		<p class="quote-author">— Nikola Tesla</p>
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

	.intro {
		background: linear-gradient(135deg, rgba(0, 212, 255, 0.1), rgba(168, 85, 247, 0.1));
		text-align: center;
		font-size: 1.1rem;
	}

	.accomplishments-grid {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.accomplishment-card {
		background: rgba(255, 255, 255, 0.05);
		border: 1px solid rgba(0, 212, 255, 0.3);
		border-radius: 12px;
		padding: 1.25rem;
		text-align: left;
		cursor: pointer;
		transition: all 0.3s ease;
		width: 100%;
	}

	.accomplishment-card:hover {
		border-color: #a855f7;
	}

	.accomplishment-card.expanded {
		border-color: #00d4ff;
		background: rgba(0, 212, 255, 0.1);
	}

	.accomplishment-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.accomplishment-header h3 {
		margin: 0;
		color: #00d4ff;
		font-size: 1rem;
	}

	.expand-icon {
		font-size: 1.5rem;
		color: #a855f7;
		font-weight: bold;
	}

	.accomplishment-details {
		margin-top: 1rem;
		animation: slideDown 0.3s ease;
	}

	.accomplishment-details p {
		margin: 0 0 0.75rem 0;
	}

	@keyframes slideDown {
		from { opacity: 0; max-height: 0; }
		to { opacity: 1; max-height: 200px; }
	}

	.impact-badge {
		display: flex;
		gap: 0.5rem;
		flex-wrap: wrap;
		align-items: center;
	}

	.impact-label {
		font-weight: 600;
		color: #a855f7;
		font-size: 0.85rem;
	}

	.impact-text {
		background: rgba(168, 85, 247, 0.2);
		padding: 0.25rem 0.75rem;
		border-radius: 20px;
		font-size: 0.85rem;
		color: rgba(240, 248, 255, 0.9);
	}

	.benefits-list {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.benefit-item {
		display: flex;
		align-items: flex-start;
		gap: 1rem;
		padding: 1rem;
		background: rgba(0, 212, 255, 0.05);
		border-radius: 8px;
		transition: all 0.3s ease;
	}

	.benefit-item:hover {
		background: rgba(0, 212, 255, 0.1);
		transform: translateX(10px);
	}

	.benefit-icon {
		font-size: 2rem;
		flex-shrink: 0;
	}

	.benefit-content h4 {
		margin: 0 0 0.25rem 0;
		color: #00d4ff;
	}

	.benefit-content p {
		margin: 0;
		font-size: 0.9rem;
		color: rgba(240, 248, 255, 0.8);
	}

	.awards-grid {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.award-card {
		text-align: center;
		transition: all 0.3s ease;
	}

	.award-card:hover {
		transform: scale(1.02);
	}

	.award-icon {
		font-size: 3rem;
	}

	.award-card h3 {
		margin: 0.5rem 0;
		color: #00d4ff;
	}

	.award-year {
		display: inline-block;
		background: rgba(168, 85, 247, 0.2);
		color: #a855f7;
		padding: 0.25rem 0.75rem;
		border-radius: 20px;
		font-size: 0.85rem;
		font-weight: 600;
	}

	.award-card p {
		margin: 0.75rem 0 0 0;
		font-size: 0.9rem;
	}

	.quote-box blockquote {
		font-size: 1.1rem;
		margin: 0;
	}

	.quote-author {
		text-align: right;
		color: #a855f7;
		font-weight: 600;
		margin-top: 1rem;
	}

	@media (min-width: 768px) {
		.accomplishments-grid {
			grid-template-columns: repeat(2, 1fr);
		}

		.benefits-list {
			grid-template-columns: repeat(2, 1fr);
		}

		.awards-grid {
			grid-template-columns: repeat(2, 1fr);
		}
	}
</style>
