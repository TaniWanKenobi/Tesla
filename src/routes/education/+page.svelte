<script lang="ts">
	const fields = [
		{ name: 'Electrical Engineering', icon: '⚡', description: 'Study of electrical systems and power' },
		{ name: 'Physics', icon: '🔬', description: 'Understanding natural laws and forces' },
		{ name: 'Applied Electromagnetism', icon: '🧲', description: 'Practical applications of magnetic fields' },
		{ name: 'Physical Chemistry', icon: '⚗️', description: 'Energy–matter interactions' },
		{ name: 'Electrochemistry', icon: '🔋', description: 'Electrical effects on materials' }
	];

	const schools = [
		{ 
			name: 'Graz University of Technology', 
			location: 'Austria',
			years: '1875-1878',
			note: 'Studied physics, mathematics, and mechanical engineering'
		},
		{ 
			name: 'Charles-Ferdinand University', 
			location: 'Prague',
			years: '1880',
			note: 'Attended philosophy lectures'
		}
	];

	let activeField = $state<number | null>(null);
</script>

<svelte:head>
	<title>Education - Nikola Tesla</title>
	<meta name="description" content="Tesla's fields of study and educational background" />
</svelte:head>

<section class="page-header">
	<h1>Education & Field of Study</h1>
	<p class="page-subtitle">The foundation of genius</p>
</section>

<section class="content">
	<div class="fields-section">
		<h2>Fields of Study</h2>
		<div class="fields-grid">
			{#each fields as field, i}
				<button 
					class="field-card"
					class:active={activeField === i}
					onmouseenter={() => activeField = i}
					onmouseleave={() => activeField = null}
				>
					<span class="field-icon">{field.icon}</span>
					<h3>{field.name}</h3>
					{#if activeField === i}
						<p class="field-description">{field.description}</p>
					{/if}
				</button>
			{/each}
		</div>
	</div>

	<div class="schools-section">
		<h2>Education</h2>
		<div class="timeline-container">
			{#each schools as school}
				<div class="school-card card">
					<div class="school-header">
						<h3>{school.name}</h3>
						<span class="location">📍 {school.location}</span>
					</div>
					<div class="school-years">{school.years}</div>
					<p class="school-note">{school.note}</p>
				</div>
			{/each}
		</div>
	</div>

	<div class="card chemistry-connection">
		<h2>Connection to Chemistry</h2>
		<p>
			Tesla's work connects strongly to chemistry through the study of how 
			<strong>electrical energy interacts with matter</strong>. This is a core concept 
			in <strong>physical chemistry</strong> and <strong>electrochemistry</strong>.
		</p>
		<div class="connection-diagram">
			<div class="concept">Electricity</div>
			<div class="arrow">→</div>
			<div class="concept">Energy Transfer</div>
			<div class="arrow">→</div>
			<div class="concept">Matter Transformation</div>
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

	.fields-grid {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.field-card {
		background: rgba(255, 255, 255, 0.05);
		border: 1px solid rgba(0, 212, 255, 0.3);
		border-radius: 12px;
		padding: 1.5rem;
		text-align: center;
		cursor: pointer;
		transition: all 0.3s ease;
		min-height: 120px;
		width: 100%;
	}

	.field-card:hover, .field-card.active {
		border-color: #00d4ff;
		background: rgba(0, 212, 255, 0.1);
		transform: translateY(-5px);
		box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
	}

	.field-icon {
		font-size: 2rem;
		display: block;
		margin-bottom: 0.5rem;
	}

	.field-card h3 {
		margin: 0;
		font-size: 1rem;
		color: #00d4ff;
	}

	.field-description {
		margin: 0.5rem 0 0 0;
		font-size: 0.85rem;
		color: rgba(240, 248, 255, 0.7);
		animation: fadeIn 0.3s ease;
	}

	@keyframes fadeIn {
		from { opacity: 0; }
		to { opacity: 1; }
	}

	.timeline-container {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		margin-top: 1rem;
	}

	.school-card {
		position: relative;
		padding-left: 2rem;
	}

	.school-card::before {
		content: '';
		position: absolute;
		left: 0;
		top: 0;
		bottom: 0;
		width: 4px;
		background: linear-gradient(180deg, #00d4ff, #a855f7);
		border-radius: 2px;
	}

	.school-header {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		align-items: center;
		gap: 0.5rem;
	}

	.school-header h3 {
		margin: 0;
		color: #00d4ff;
	}

	.location {
		font-size: 0.9rem;
		color: rgba(240, 248, 255, 0.7);
	}

	.school-years {
		display: inline-block;
		background: rgba(168, 85, 247, 0.2);
		color: #a855f7;
		padding: 0.25rem 0.75rem;
		border-radius: 20px;
		font-size: 0.85rem;
		font-weight: 600;
		margin: 0.5rem 0;
	}

	.school-note {
		margin: 0.5rem 0 0 0;
		color: rgba(240, 248, 255, 0.8);
	}

	.chemistry-connection {
		background: linear-gradient(135deg, rgba(168, 85, 247, 0.1), rgba(0, 212, 255, 0.1));
	}

	.connection-diagram {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-wrap: wrap;
		gap: 0.5rem;
		margin-top: 1.5rem;
	}

	.concept {
		background: rgba(0, 212, 255, 0.2);
		border: 1px solid #00d4ff;
		padding: 0.75rem 1rem;
		border-radius: 8px;
		font-weight: 600;
		color: #00d4ff;
	}

	.arrow {
		color: #a855f7;
		font-size: 1.5rem;
	}

	@media (min-width: 768px) {
		.fields-grid {
			grid-template-columns: repeat(3, 1fr);
		}

		.fields-grid .field-card:nth-child(4),
		.fields-grid .field-card:nth-child(5) {
			grid-column: span 1;
		}
	}

	@media (min-width: 1024px) {
		.fields-grid {
			grid-template-columns: repeat(5, 1fr);
		}
	}
</style>
