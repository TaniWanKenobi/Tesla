<script lang="ts">
	let expandedSection = $state<string | null>(null);
	
	function toggleSection(section: string) {
		expandedSection = expandedSection === section ? null : section;
	}
</script>

<svelte:head>
	<title>Early Life - Nikola Tesla</title>
	<meta name="description" content="Learn about Nikola Tesla's birthplace, family, and childhood" />
</svelte:head>

<section class="page-header">
	<h1>Early Life & Birthplace</h1>
	<p class="page-subtitle">The origins of a genius</p>
</section>

<section class="content">
	<div class="card main-content">
		<h2>Birthplace, Family, and Childhood</h2>
		
		<p>
			Nikola Tesla was born on <strong>July 10, 1856</strong> in <strong>Smiljan</strong>, 
			a village in the Austrian Empire (modern-day Croatia). He was born during a fierce 
			lightning storm, a fitting omen for a man who would later harness the power of electricity.
		</p>

		<p>
			He was born into a <strong>Serbian family</strong> with deep roots in the Orthodox 
			Christian tradition. His heritage and upbringing would shape his character and 
			his relentless pursuit of knowledge.
		</p>
	</div>

	<div class="interactive-cards">
		<button 
			class="expand-card" 
			class:expanded={expandedSection === 'father'}
			onclick={() => toggleSection('father')}
		>
			<h3>👨 His Father</h3>
			{#if expandedSection === 'father'}
				<div class="expanded-content">
					<p>
						<strong>Milutin Tesla</strong> was a Serbian Orthodox priest and a writer. 
						He was known for his eloquent sermons and his ability to recite long passages 
						from memory, a trait young Nikola would inherit.
					</p>
				</div>
			{:else}
				<span class="hint">Click to learn more</span>
			{/if}
		</button>

		<button 
			class="expand-card"
			class:expanded={expandedSection === 'mother'}
			onclick={() => toggleSection('mother')}
		>
			<h3>👩 His Mother</h3>
			{#if expandedSection === 'mother'}
				<div class="expanded-content">
					<p>
						<strong>Đuka Tesla</strong>, although not formally educated, was highly 
						intelligent and inventive. She created small household tools and devices 
						to make daily life easier. Tesla credited her with sparking his inventive 
						spirit and eidetic memory.
					</p>
				</div>
			{:else}
				<span class="hint">Click to learn more</span>
			{/if}
		</button>

		<button 
			class="expand-card"
			class:expanded={expandedSection === 'childhood'}
			onclick={() => toggleSection('childhood')}
		>
			<h3>💵 Childhood Traits</h3>
			{#if expandedSection === 'childhood'}
				<div class="expanded-content">
					<ul>
						<li><strong>Photographic memory</strong> : could visualize objects in perfect detail</li>
						<li><strong>Fascination with science</strong> : especially electricity and mechanical devices</li>
						<li><strong>Exceptional creativity</strong> : invented gadgets as a child</li>
						<li><strong>Vivid imagination</strong> : experienced flashes of light and visions</li>
					</ul>
				</div>
			{:else}
				<span class="hint">Click to learn more</span>
			{/if}
		</button>
	</div>

	<div class="card highlight-box">
		<h3>⚡ Key Influence</h3>
		<p>
			These early influences (his father's intellect, his mother's inventiveness, and his 
			own extraordinary mental abilities) <strong>shaped Tesla's future scientific career and his 
			revolutionary approach to invention.</strong>
		</p>
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

	.main-content p {
		margin: 1rem 0;
	}

	.interactive-cards {
		display: grid;
		gap: 1rem;
	}

	.expand-card {
		background: rgba(255, 255, 255, 0.05);
		border: 1px solid rgba(0, 212, 255, 0.3);
		border-radius: 12px;
		padding: 1.5rem;
		text-align: left;
		cursor: pointer;
		transition: all 0.3s ease;
		width: 100%;
	}

	.expand-card:hover {
		border-color: #a855f7;
		box-shadow: 0 0 20px rgba(168, 85, 247, 0.2);
	}

	.expand-card.expanded {
		border-color: #00d4ff;
		background: rgba(0, 212, 255, 0.1);
	}

	.expand-card h3 {
		margin: 0 0 0.5rem 0;
		color: #00d4ff;
	}

	.hint {
		font-size: 0.85rem;
		color: rgba(240, 248, 255, 0.5);
	}

	.expanded-content {
		margin-top: 1rem;
		animation: fadeIn 0.3s ease;
	}

	.expanded-content p {
		margin: 0;
	}

	.expanded-content ul {
		margin: 0;
		padding-left: 0;
	}

	@keyframes fadeIn {
		from { opacity: 0; transform: translateY(-10px); }
		to { opacity: 1; transform: translateY(0); }
	}

	.highlight-box {
		background: linear-gradient(135deg, rgba(0, 212, 255, 0.1), rgba(168, 85, 247, 0.1));
		border-color: #a855f7;
	}

	.highlight-box h3 {
		color: #a855f7;
		margin-top: 0;
	}

	@media (min-width: 768px) {
		.interactive-cards {
			grid-template-columns: repeat(3, 1fr);
		}
	}
</style>
