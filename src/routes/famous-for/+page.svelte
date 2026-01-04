<script lang="ts">
	import highVoltage from '$lib/images/highvoltageelectricity.png';
	import electromagnet from '$lib/images/electromagnet.png';
	import particles from '$lib/images/particles.png';

	let showDetails = $state(false);
	let currentSlide = $state(0);

	const galleryImages = [
		{ src: highVoltage, alt: 'High Voltage Electricity', caption: 'High-voltage electrical experiments' },
		{ src: electromagnet, alt: 'Electromagnetic Fields', caption: 'Electromagnetic field visualization' },
		{ src: particles, alt: 'Charged Particles', caption: 'Behavior of charged particles' }
	];

	function nextSlide() {
		currentSlide = (currentSlide + 1) % galleryImages.length;
	}

	function prevSlide() {
		currentSlide = (currentSlide - 1 + galleryImages.length) % galleryImages.length;
	}

	function goToSlide(index: number) {
		currentSlide = index;
	}
</script>

<svelte:head>
	<title>What Tesla Is Famous For - Nikola Tesla</title>
	<meta name="description" content="Tesla's most famous inventions and contributions" />
</svelte:head>

<section class="page-header">
	<h1>What Tesla Is Most Famous For</h1>
	<p class="page-subtitle">Revolutionary innovations that changed the world</p>
</section>

<section class="content">
	<div class="main-invention card">
		<h2>⚡ The Alternating Current (AC) System</h2>
		<p>
			Nikola Tesla is most famous for developing the <strong>alternating current (AC) 
			electrical system</strong>, which allows electricity to be transmitted efficiently 
			over long distances. Before AC, direct current (DC) could only travel short distances, 
			limiting electrification to small areas.
		</p>
		
		<button class="toggle-button" onclick={() => showDetails = !showDetails}>
			{showDetails ? 'Hide Technical Details' : 'Show Technical Details'} 
			<span class="arrow">{showDetails ? '▲' : '▼'}</span>
		</button>

		{#if showDetails}
			<div class="technical-details">
				<h3>How AC Works</h3>
				<div class="comparison">
					<div class="comparison-item">
						<h4>DC (Direct Current)</h4>
						<div class="visual dc-visual">→→→→→→→</div>
						<p>Flows in one direction only</p>
						<p class="con">❌ Loses power over distance</p>
					</div>
					<div class="vs">VS</div>
					<div class="comparison-item">
						<h4>AC (Alternating Current)</h4>
						<div class="visual ac-visual">↔↔↔↔↔↔↔</div>
						<p>Reverses direction periodically</p>
						<p class="pro">✓ Travels efficiently over long distances</p>
					</div>
				</div>
			</div>
		{/if}
	</div>

	<div class="work-areas">
		<h2>Areas of Expertise</h2>
		<div class="areas-grid">
			<div class="area-card card">
				<span class="area-icon">🔌</span>
				<h3>High-Voltage Electricity</h3>
				<p>Mastered the control of extremely high voltages for power transmission</p>
			</div>
			<div class="area-card card">
				<span class="area-icon">🧲</span>
				<h3>Electromagnetic Fields</h3>
				<p>Pioneered understanding of magnetic field behavior and applications</p>
			</div>
			<div class="area-card card">
				<span class="area-icon">⚛️</span>
				<h3>Charged Particles</h3>
				<p>Studied the behavior of electrons and ions in electrical systems</p>
			</div>
		</div>
	</div>

	<div class="gallery-section">
		<h2>Visual Gallery</h2>
		<div class="carousel">
			<button class="carousel-btn prev" onclick={prevSlide} aria-label="Previous image">
				‹
			</button>
			
			<div class="carousel-container">
				<div class="carousel-track" style="transform: translateX(-{currentSlide * 100}%)">
					{#each galleryImages as image, i}
						<div class="carousel-slide">
							<img src={image.src} alt={image.alt} />
							<p class="slide-caption">{image.caption}</p>
						</div>
					{/each}
				</div>
			</div>
			
			<button class="carousel-btn next" onclick={nextSlide} aria-label="Next image">
				›
			</button>
		</div>
		
		<div class="carousel-dots">
			{#each galleryImages as _, i}
				<button 
					class="dot" 
					class:active={currentSlide === i}
					onclick={() => goToSlide(i)}
					aria-label="Go to slide {i + 1}"
				></button>
			{/each}
		</div>
	</div>

	<div class="chemistry-link card">
		<h2>Connection to Physical Chemistry</h2>
		<p>
			These principles are essential to <strong>physical chemistry</strong>, as they 
			explain how energy interacts with atoms, molecules, and materials. Understanding 
			electrical forces at the molecular level is fundamental to chemical reactions 
			and material science.
		</p>
	</div>

	<div class="tesla-coil card">
		<h2>The Tesla Coil</h2>
		<div class="coil-content">
			<div class="coil-visual">
				<div class="coil-animation">
					<div class="spark spark-1"></div>
					<div class="spark spark-2"></div>
					<div class="spark spark-3"></div>
					<div class="coil-base">⚡</div>
				</div>
			</div>
			<div class="coil-description">
				<p>
					Tesla also invented the <strong>Tesla coil</strong>, which demonstrates 
					high-frequency electrical discharge and plasma formation. This device 
					produces spectacular electrical arcs and was crucial in the development 
					of radio technology.
				</p>
				<div class="coil-facts">
					<span class="fact">🔬 High-frequency resonant transformer</span>
					<span class="fact">💜 Creates plasma arcs</span>
					<span class="fact">📻 Foundation for radio</span>
				</div>
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

	.main-invention {
		background: linear-gradient(135deg, rgba(0, 212, 255, 0.1), rgba(168, 85, 247, 0.1));
	}

	.toggle-button {
		margin-top: 1rem;
		background: rgba(0, 212, 255, 0.2);
		border: 1px solid #00d4ff;
		color: #00d4ff;
		padding: 0.75rem 1.5rem;
		border-radius: 8px;
		cursor: pointer;
		transition: all 0.3s ease;
		display: flex;
		align-items: center;
		gap: 0.5rem;
	}

	.toggle-button:hover {
		background: rgba(0, 212, 255, 0.3);
	}

	.arrow {
		font-size: 0.8rem;
	}

	.technical-details {
		margin-top: 1.5rem;
		padding-top: 1.5rem;
		border-top: 1px solid rgba(0, 212, 255, 0.3);
		animation: slideDown 0.3s ease;
	}

	@keyframes slideDown {
		from { opacity: 0; max-height: 0; }
		to { opacity: 1; max-height: 500px; }
	}

	.comparison {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 1rem;
		margin-top: 1rem;
	}

	.comparison-item {
		text-align: center;
		padding: 1rem;
		background: rgba(255, 255, 255, 0.05);
		border-radius: 12px;
		width: 100%;
	}

	.comparison-item h4 {
		margin: 0 0 0.5rem 0;
		color: #00d4ff;
	}

	.visual {
		font-family: monospace;
		font-size: 1.5rem;
		padding: 0.5rem;
		margin: 0.5rem 0;
	}

	.dc-visual {
		color: #ff6b6b;
	}

	.ac-visual {
		color: #00d4ff;
		animation: pulse 1s infinite;
	}

	@keyframes pulse {
		0%, 100% { opacity: 1; }
		50% { opacity: 0.5; }
	}

	.con {
		color: #ff6b6b;
	}

	.pro {
		color: #00d4ff;
	}

	.vs {
		font-size: 1.5rem;
		font-weight: 700;
		color: #a855f7;
	}

	.areas-grid {
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
	}

	.area-card {
		text-align: center;
		transition: all 0.3s ease;
	}

	.area-card:hover {
		transform: scale(1.02);
	}

	.area-icon {
		font-size: 2.5rem;
		display: block;
		margin-bottom: 0.5rem;
	}

	.area-card h3 {
		color: #00d4ff;
		margin: 0.5rem 0;
	}

	.area-card p {
		margin: 0;
		font-size: 0.9rem;
	}

	.chemistry-link {
		border-left: 4px solid #a855f7;
	}

	.coil-content {
		display: flex;
		flex-direction: column;
		gap: 2rem;
		align-items: center;
	}

	.coil-visual {
		flex-shrink: 0;
	}

	.coil-animation {
		position: relative;
		width: 150px;
		height: 150px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.coil-base {
		font-size: 4rem;
		animation: glow 2s infinite;
	}

	@keyframes glow {
		0%, 100% { 
			text-shadow: 0 0 20px #00d4ff, 0 0 40px #a855f7;
		}
		50% { 
			text-shadow: 0 0 40px #00d4ff, 0 0 80px #a855f7, 0 0 100px #00d4ff;
		}
	}

	.spark {
		position: absolute;
		width: 2px;
		height: 30px;
		background: linear-gradient(to top, transparent, #00d4ff, #a855f7);
		animation: spark 0.5s infinite;
	}

	.spark-1 {
		top: 10px;
		left: 50%;
		transform: rotate(-30deg);
		animation-delay: 0s;
	}

	.spark-2 {
		top: 20px;
		right: 20px;
		transform: rotate(30deg);
		animation-delay: 0.2s;
	}

	.spark-3 {
		top: 20px;
		left: 20px;
		transform: rotate(-60deg);
		animation-delay: 0.4s;
	}

	@keyframes spark {
		0%, 100% { opacity: 0; height: 20px; }
		50% { opacity: 1; height: 40px; }
	}

	.coil-facts {
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem;
		margin-top: 1rem;
	}

	.fact {
		background: rgba(0, 212, 255, 0.1);
		border: 1px solid rgba(0, 212, 255, 0.3);
		padding: 0.5rem 1rem;
		border-radius: 20px;
		font-size: 0.85rem;
	}

	@media (min-width: 768px) {
		.comparison {
			flex-direction: row;
		}

		.comparison-item {
			flex: 1;
		}

		.areas-grid {
			grid-template-columns: repeat(3, 1fr);
		}

		.coil-content {
			flex-direction: row;
		}
	}

	/* Carousel Styles */
	.gallery-section {
		margin: 2rem 0;
	}

	.gallery-section h2 {
		text-align: center;
		margin-bottom: 1.5rem;
	}

	.carousel {
		display: flex;
		align-items: center;
		gap: 1rem;
		max-width: 800px;
		margin: 0 auto;
	}

	.carousel-container {
		flex: 1;
		overflow: hidden;
		border-radius: 12px;
		border: 2px solid rgba(0, 212, 255, 0.3);
	}

	.carousel-track {
		display: flex;
		transition: transform 0.5s ease;
	}

	.carousel-slide {
		min-width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.carousel-slide img {
		width: 100%;
		max-height: 400px;
		object-fit: contain;
		background: rgba(10, 10, 30, 0.8);
	}

	.slide-caption {
		padding: 1rem;
		margin: 0;
		background: rgba(0, 212, 255, 0.1);
		width: 100%;
		text-align: center;
		color: #00d4ff;
		font-weight: 500;
	}

	.carousel-btn {
		width: 50px;
		height: 50px;
		border-radius: 50%;
		background: rgba(0, 212, 255, 0.2);
		border: 2px solid #00d4ff;
		color: #00d4ff;
		font-size: 2rem;
		cursor: pointer;
		transition: all 0.3s ease;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-shrink: 0;
	}

	.carousel-btn:hover {
		background: rgba(0, 212, 255, 0.4);
		transform: scale(1.1);
		box-shadow: 0 0 20px rgba(0, 212, 255, 0.5);
	}

	.carousel-dots {
		display: flex;
		justify-content: center;
		gap: 0.75rem;
		margin-top: 1rem;
	}

	.dot {
		width: 12px;
		height: 12px;
		border-radius: 50%;
		background: rgba(0, 212, 255, 0.3);
		border: none;
		cursor: pointer;
		transition: all 0.3s ease;
	}

	.dot:hover {
		background: rgba(0, 212, 255, 0.6);
	}

	.dot.active {
		background: #00d4ff;
		box-shadow: 0 0 10px rgba(0, 212, 255, 0.8);
		transform: scale(1.2);
	}
</style>
