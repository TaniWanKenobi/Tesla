<script lang="ts">
	const concepts = [
		{
			name: 'Alternating Current (AC)',
			description: 'Electric current that periodically reverses direction, enabling efficient long-distance power transmission',
			icon: '⚡'
		},
		{
			name: 'Electromagnetic Induction',
			description: 'The production of voltage across a conductor when it is exposed to a changing magnetic field',
			icon: '🧲'
		},
		{
			name: 'Plasma (Ionized Gas)',
			description: 'A state of matter where gas becomes electrically conductive due to ionization',
			icon: '💜'
		},
		{
			name: 'Electric Charge Movement',
			description: 'The flow of electrons through conductors, fundamental to all electrical phenomena',
			icon: '⚛️'
		}
	];

	let activeVisual = $state(0);
</script>

<svelte:head>
	<title>Chemistry Connections - Nikola Tesla</title>
	<meta name="description" content="Visual evidence and chemistry connections in Tesla's work" />
</svelte:head>

<section class="page-header">
	<h1>Chemistry Connections & Visual Evidence</h1>
	<p class="page-subtitle">Where physics meets chemistry</p>
</section>

<section class="content">
	<div class="visuals-section">
		<h2>Scientific Diagrams</h2>
		<p>The following visuals illustrate key concepts from Tesla's work:</p>

		<div class="visual-tabs">
			<button 
				class="visual-tab" 
				class:active={activeVisual === 0}
				onclick={() => activeVisual = 0}
			>
				AC Power System
			</button>
			<button 
				class="visual-tab"
				class:active={activeVisual === 1}
				onclick={() => activeVisual = 1}
			>
				Tesla Coil
			</button>
			<button 
				class="visual-tab"
				class:active={activeVisual === 2}
				onclick={() => activeVisual = 2}
			>
				Electromagnetic Field
			</button>
		</div>

		<div class="visual-display card">
			{#if activeVisual === 0}
				<div class="diagram ac-diagram">
					<h3>Alternating Current Power System</h3>
					<div class="ac-visual-container">
						<div class="ac-component generator">
							<div class="component-icon">🏭</div>
							<span>Generator</span>
						</div>
						<div class="ac-flow">
							<div class="wave-animation"></div>
						</div>
						<div class="ac-component transformer">
							<div class="component-icon">⚡</div>
							<span>Step-Up Transformer</span>
						</div>
						<div class="ac-flow long">
							<div class="wave-animation"></div>
							<span class="distance-label">Long Distance</span>
						</div>
						<div class="ac-component transformer">
							<div class="component-icon">⚡</div>
							<span>Step-Down Transformer</span>
						</div>
						<div class="ac-flow">
							<div class="wave-animation"></div>
						</div>
						<div class="ac-component home">
							<div class="component-icon">🏠</div>
							<span>Homes & Industry</span>
						</div>
					</div>
					<p class="diagram-note">AC allows voltage to be increased for transmission, reducing power loss over distance</p>
				</div>
			{:else if activeVisual === 1}
				<div class="diagram tesla-coil-diagram">
					<h3>Tesla Coil Producing Plasma Arcs</h3>
					<div class="coil-diagram-container">
						<div class="coil-primary">
							<span>Primary Coil</span>
							<div class="coil-wrap primary"></div>
						</div>
						<div class="coil-secondary">
							<span>Secondary Coil</span>
							<div class="coil-wrap secondary"></div>
						</div>
						<div class="plasma-output">
							<div class="plasma-arc arc-1"></div>
							<div class="plasma-arc arc-2"></div>
							<div class="plasma-arc arc-3"></div>
							<span>Plasma Discharge</span>
						</div>
					</div>
					<div class="coil-labels">
						<span class="label">Input: Low Voltage AC</span>
						<span class="label">Output: High Frequency, High Voltage</span>
					</div>
				</div>
			{:else}
				<div class="diagram em-field-diagram">
					<h3>Electromagnetic Field Around a Conductor</h3>
					<div class="conductor-diagram">
						<div class="field-lines">
							<div class="field-line line-1"></div>
							<div class="field-line line-2"></div>
							<div class="field-line line-3"></div>
						</div>
						<div class="conductor">
							<span class="current-arrow">→ I</span>
						</div>
						<div class="field-direction">
							<span>B (Magnetic Field)</span>
							<div class="direction-arrow">↻</div>
						</div>
					</div>
					<p class="diagram-note">Current flowing through a conductor creates a circular magnetic field around it (Right-hand rule)</p>
				</div>
			{/if}
		</div>
	</div>

	<div class="concepts-section">
		<h2>Scientific Concepts</h2>
		<div class="concepts-grid">
			{#each concepts as concept}
				<div class="concept-card card">
					<span class="concept-icon">{concept.icon}</span>
					<h3>{concept.name}</h3>
					<p>{concept.description}</p>
				</div>
			{/each}
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

	.visual-tabs {
		display: flex;
		gap: 0.5rem;
		margin: 1rem 0;
		flex-wrap: wrap;
	}

	.visual-tab {
		background: rgba(255, 255, 255, 0.05);
		border: 1px solid rgba(0, 212, 255, 0.3);
		color: rgba(240, 248, 255, 0.8);
		padding: 0.75rem 1rem;
		border-radius: 8px;
		cursor: pointer;
		transition: all 0.3s ease;
		font-size: 0.9rem;
	}

	.visual-tab:hover {
		border-color: #00d4ff;
	}

	.visual-tab.active {
		background: linear-gradient(90deg, #00d4ff, #a855f7);
		color: white;
		border-color: transparent;
	}

	.visual-display {
		min-height: 300px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.diagram {
		width: 100%;
		text-align: center;
	}

	.diagram h3 {
		color: #00d4ff;
		margin-bottom: 1.5rem;
	}

	.diagram-note {
		font-size: 0.9rem;
		color: rgba(240, 248, 255, 0.7);
		font-style: italic;
		margin-top: 1.5rem;
	}

	/* AC Diagram Styles */
	.ac-visual-container {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 0.5rem;
		flex-wrap: wrap;
		padding: 1rem;
	}

	.ac-component {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 0.25rem;
	}

	.component-icon {
		font-size: 2rem;
	}

	.ac-component span {
		font-size: 0.75rem;
		color: rgba(240, 248, 255, 0.8);
	}

	.ac-flow {
		width: 40px;
		height: 20px;
		position: relative;
		overflow: hidden;
	}

	.ac-flow.long {
		width: 80px;
	}

	.wave-animation {
		width: 100%;
		height: 2px;
		background: linear-gradient(90deg, #00d4ff, #a855f7, #00d4ff);
		animation: wave 1s infinite linear;
	}

	@keyframes wave {
		0% { transform: translateX(-50%); }
		100% { transform: translateX(0); }
	}

	.distance-label {
		position: absolute;
		top: 8px;
		left: 50%;
		transform: translateX(-50%);
		font-size: 0.6rem;
		color: #a855f7;
		white-space: nowrap;
	}

	/* Tesla Coil Diagram */
	.coil-diagram-container {
		display: flex;
		align-items: flex-end;
		justify-content: center;
		gap: 1rem;
		padding: 1rem;
	}

	.coil-primary, .coil-secondary {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 0.5rem;
	}

	.coil-primary span, .coil-secondary span {
		font-size: 0.75rem;
		color: rgba(240, 248, 255, 0.8);
	}

	.coil-wrap {
		border: 3px solid;
		border-radius: 4px;
	}

	.coil-wrap.primary {
		width: 50px;
		height: 30px;
		border-color: #00d4ff;
	}

	.coil-wrap.secondary {
		width: 30px;
		height: 60px;
		border-color: #a855f7;
	}

	.plasma-output {
		position: relative;
		width: 80px;
		height: 80px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-end;
	}

	.plasma-output span {
		font-size: 0.75rem;
		color: #a855f7;
	}

	.plasma-arc {
		position: absolute;
		width: 2px;
		background: linear-gradient(to top, #a855f7, #00d4ff, transparent);
		animation: arc 0.5s infinite;
	}

	.arc-1 { left: 30%; height: 40px; top: 0; animation-delay: 0s; }
	.arc-2 { left: 50%; height: 50px; top: 0; animation-delay: 0.2s; }
	.arc-3 { left: 70%; height: 35px; top: 0; animation-delay: 0.4s; }

	@keyframes arc {
		0%, 100% { opacity: 0.3; }
		50% { opacity: 1; }
	}

	.coil-labels {
		display: flex;
		justify-content: space-around;
		margin-top: 1rem;
		flex-wrap: wrap;
		gap: 0.5rem;
	}

	.label {
		font-size: 0.8rem;
		padding: 0.25rem 0.75rem;
		background: rgba(0, 212, 255, 0.1);
		border-radius: 4px;
	}

	/* EM Field Diagram */
	.conductor-diagram {
		position: relative;
		width: 200px;
		height: 200px;
		margin: 0 auto;
	}

	.field-lines {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
	}

	.field-line {
		position: absolute;
		border: 2px dashed;
		border-radius: 50%;
		animation: fieldPulse 2s infinite;
	}

	.line-1 { width: 80px; height: 80px; border-color: rgba(0, 212, 255, 0.8); top: -40px; left: -40px; }
	.line-2 { width: 120px; height: 120px; border-color: rgba(0, 212, 255, 0.5); top: -60px; left: -60px; animation-delay: 0.3s; }
	.line-3 { width: 160px; height: 160px; border-color: rgba(0, 212, 255, 0.3); top: -80px; left: -80px; animation-delay: 0.6s; }

	@keyframes fieldPulse {
		0%, 100% { opacity: 1; }
		50% { opacity: 0.5; }
	}

	.conductor {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		width: 20px;
		height: 20px;
		background: #a855f7;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.current-arrow {
		color: white;
		font-size: 0.7rem;
		font-weight: bold;
	}

	.field-direction {
		position: absolute;
		bottom: 10px;
		left: 50%;
		transform: translateX(-50%);
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.field-direction span {
		font-size: 0.8rem;
		color: #00d4ff;
	}

	.direction-arrow {
		font-size: 1.5rem;
		color: #00d4ff;
		animation: rotate 3s infinite linear;
	}

	@keyframes rotate {
		from { transform: rotate(0deg); }
		to { transform: rotate(360deg); }
	}

	/* Concepts Grid */
	.concepts-grid {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.concept-card {
		text-align: center;
		transition: all 0.3s ease;
	}

	.concept-card:hover {
		transform: translateY(-5px);
	}

	.concept-icon {
		font-size: 2.5rem;
		display: block;
		margin-bottom: 0.5rem;
	}

	.concept-card h3 {
		color: #00d4ff;
		margin: 0.5rem 0;
		font-size: 1rem;
	}

	.concept-card p {
		margin: 0;
		font-size: 0.85rem;
		color: rgba(240, 248, 255, 0.8);
	}

	@media (min-width: 768px) {
		.concepts-grid {
			grid-template-columns: repeat(2, 1fr);
		}
	}

	@media (min-width: 1024px) {
		.concepts-grid {
			grid-template-columns: repeat(4, 1fr);
		}
	}
</style>
