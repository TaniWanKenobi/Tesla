<script lang="ts">
	const facts = [
		{
			fact: 'Tesla held over 300 patents worldwide',
			detail: 'His inventions span electrical power, motors, lighting, wireless communication, and more',
			icon: '📜'
		},
		{
			fact: 'He could visualize entire inventions in his mind before building them',
			detail: 'Tesla possessed an extraordinary ability to mentally construct and test machines in perfect detail',
			icon: '🧠'
		},
		{
			fact: 'Tesla slept only about two hours per night',
			detail: 'He claimed to never sleep more than 2 hours at a time, sometimes taking short naps during the day',
			icon: '😴'
		},
		{
			fact: 'He had an intense fear of germs and disliked physical contact',
			detail: 'Tesla was known for his germaphobia and various obsessive-compulsive behaviors',
			icon: '🦠'
		},
		{
			fact: 'Tesla never married and dedicated his life to science',
			detail: 'He believed that celibacy helped him focus on his work and scientific pursuits',
			icon: '💍'
		},
		{
			fact: 'He predicted wireless communication long before modern technology',
			detail: 'Tesla envisioned smartphones, Wi-Fi, and the internet decades before they existed',
			icon: '📱'
		}
	];

	let revealedFacts = $state<Set<number>>(new Set());
	let allRevealed = $state(false);

	function toggleFact(index: number) {
		const newSet = new Set(revealedFacts);
		if (newSet.has(index)) {
			newSet.delete(index);
		} else {
			newSet.add(index);
		}
		revealedFacts = newSet;
	}

	function revealAll() {
		if (allRevealed) {
			revealedFacts = new Set();
			allRevealed = false;
		} else {
			revealedFacts = new Set(facts.map((_, i) => i));
			allRevealed = true;
		}
	}
</script>

<svelte:head>
	<title>Interesting Facts - Nikola Tesla</title>
	<meta name="description" content="Fascinating facts about Nikola Tesla's life and personality" />
</svelte:head>

<section class="page-header">
	<h1>Interesting Facts</h1>
	<p class="page-subtitle">The extraordinary life of a genius</p>
</section>

<section class="content">
	<div class="controls">
		<button class="reveal-all-btn" onclick={revealAll}>
			{allRevealed ? 'Hide All Details' : 'Reveal All Details'}
		</button>
	</div>

	<div class="facts-grid">
		{#each facts as item, i}
			<button 
				class="fact-card"
				class:revealed={revealedFacts.has(i)}
				onclick={() => toggleFact(i)}
			>
				<div class="fact-icon">{item.icon}</div>
				<div class="fact-content">
					<p class="fact-text">{item.fact}</p>
					{#if revealedFacts.has(i)}
						<p class="fact-detail">{item.detail}</p>
					{:else}
						<span class="tap-hint">Tap to learn more</span>
					{/if}
				</div>
			</button>
		{/each}
	</div>

	<div class="bonus-facts card">
		<h2>More About Tesla</h2>
		<div class="bonus-grid">
			<div class="bonus-item">
				<span class="bonus-icon">🗣️</span>
				<p>Spoke <strong>8 languages</strong> fluently</p>
			</div>
			<div class="bonus-item">
				<span class="bonus-icon">🕊️</span>
				<p>Had a special <strong>bond with pigeons</strong>, especially one white pigeon he claimed to love</p>
			</div>
			<div class="bonus-item">
				<span class="bonus-icon">🔢</span>
				<p>Was <strong>obsessed with the number 3</strong> and numbers divisible by 3</p>
			</div>
			<div class="bonus-item">
				<span class="bonus-icon">⚡</span>
				<p>Born during a <strong>lightning storm</strong></p>
			</div>
			<div class="bonus-item">
				<span class="bonus-icon">📏</span>
				<p>Was <strong>6 feet 2 inches</strong> tall and strikingly thin</p>
			</div>
			<div class="bonus-item">
				<span class="bonus-icon">🎩</span>
				<p>Known for his <strong>impeccable fashion</strong> and elegant appearance</p>
			</div>
		</div>
	</div>

	<div class="appearance-section card">
		<h2>Physical Appearance</h2>
		<div class="appearance-details">
			<div class="appearance-item">
				<span class="label">Height</span>
				<span class="value">6'2" (188 cm)</span>
			</div>
			<div class="appearance-item">
				<span class="label">Build</span>
				<span class="value">Tall and slender</span>
			</div>
			<div class="appearance-item">
				<span class="label">Eyes</span>
				<span class="value">Light gray-blue</span>
			</div>
			<div class="appearance-item">
				<span class="label">Hair</span>
				<span class="value">Jet black (later gray)</span>
			</div>
			<div class="appearance-item">
				<span class="label">Style</span>
				<span class="value">Impeccably dressed</span>
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

	.controls {
		text-align: center;
	}

	.reveal-all-btn {
		background: linear-gradient(90deg, #00d4ff, #a855f7);
		color: white;
		border: none;
		padding: 0.75rem 2rem;
		border-radius: 25px;
		cursor: pointer;
		font-weight: 600;
		transition: all 0.3s ease;
	}

	.reveal-all-btn:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 20px rgba(0, 212, 255, 0.4);
	}

	.facts-grid {
		display: grid;
		gap: 1rem;
	}

	.fact-card {
		background: rgba(255, 255, 255, 0.05);
		border: 1px solid rgba(0, 212, 255, 0.3);
		border-radius: 12px;
		padding: 1.5rem;
		display: flex;
		align-items: flex-start;
		gap: 1rem;
		cursor: pointer;
		transition: all 0.3s ease;
		text-align: left;
		width: 100%;
	}

	.fact-card:hover {
		border-color: #a855f7;
		transform: translateY(-2px);
	}

	.fact-card.revealed {
		border-color: #00d4ff;
		background: rgba(0, 212, 255, 0.1);
	}

	.fact-icon {
		font-size: 2rem;
		flex-shrink: 0;
	}

	.fact-content {
		flex: 1;
	}

	.fact-text {
		margin: 0;
		font-weight: 500;
		color: rgba(240, 248, 255, 0.95);
	}

	.fact-detail {
		margin: 0.75rem 0 0 0;
		color: rgba(240, 248, 255, 0.7);
		font-size: 0.9rem;
		animation: fadeIn 0.3s ease;
	}

	.tap-hint {
		display: block;
		margin-top: 0.5rem;
		font-size: 0.8rem;
		color: rgba(0, 212, 255, 0.6);
	}

	@keyframes fadeIn {
		from { opacity: 0; transform: translateY(-5px); }
		to { opacity: 1; transform: translateY(0); }
	}

	.bonus-facts h2 {
		text-align: center;
	}

	.bonus-grid {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.bonus-item {
		display: flex;
		align-items: center;
		gap: 1rem;
		padding: 1rem;
		background: rgba(0, 212, 255, 0.05);
		border-radius: 8px;
		transition: all 0.3s ease;
	}

	.bonus-item:hover {
		background: rgba(168, 85, 247, 0.1);
		transform: translateX(5px);
	}

	.bonus-icon {
		font-size: 1.5rem;
		flex-shrink: 0;
	}

	.bonus-item p {
		margin: 0;
	}

	.appearance-section h2 {
		text-align: center;
	}

	.appearance-details {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.appearance-item {
		display: flex;
		justify-content: space-between;
		padding: 1rem;
		background: rgba(0, 212, 255, 0.05);
		border-radius: 8px;
		border-left: 3px solid #a855f7;
	}

	.appearance-item .label {
		color: rgba(240, 248, 255, 0.6);
		font-weight: 500;
	}

	.appearance-item .value {
		color: #00d4ff;
		font-weight: 600;
	}

	@media (min-width: 768px) {
		.facts-grid {
			grid-template-columns: repeat(2, 1fr);
		}

		.bonus-grid {
			grid-template-columns: repeat(2, 1fr);
		}

		.appearance-details {
			grid-template-columns: repeat(3, 1fr);
		}
	}

	@media (min-width: 1024px) {
		.bonus-grid {
			grid-template-columns: repeat(3, 1fr);
		}
	}
</style>
