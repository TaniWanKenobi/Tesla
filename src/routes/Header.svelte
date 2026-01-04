<script lang="ts">
	import { resolve } from '$app/paths';
	import { page } from '$app/state';
</script>

<header>
	<div class="logo">
		<a href={resolve('/')}>
			<span class="logo-icon">⚡</span>
			<span class="logo-text">Nikola Tesla</span>
		</a>
	</div>

	<nav>
		<ul>
			<li aria-current={page.url.pathname === '/' ? 'page' : undefined}>
				<a href={resolve('/')}>Home</a>
			</li>
			<li aria-current={page.url.pathname === '/early-life' ? 'page' : undefined}>
				<a href={resolve('/early-life')}>Early Life</a>
			</li>
			<li aria-current={page.url.pathname === '/education' ? 'page' : undefined}>
				<a href={resolve('/education')}>Education</a>
			</li>
			<li aria-current={page.url.pathname === '/research' ? 'page' : undefined}>
				<a href={resolve('/research')}>Research</a>
			</li>
			<li aria-current={page.url.pathname === '/famous-for' ? 'page' : undefined}>
				<a href={resolve('/famous-for')}>Famous For</a>
			</li>
			<li aria-current={page.url.pathname === '/chemistry' ? 'page' : undefined}>
				<a href={resolve('/chemistry')}>Chemistry</a>
			</li>
			<li aria-current={page.url.pathname === '/accomplishments' ? 'page' : undefined}>
				<a href={resolve('/accomplishments')}>Accomplishments</a>
			</li>
			<li aria-current={page.url.pathname === '/facts' ? 'page' : undefined}>
				<a href={resolve('/facts')}>Facts</a>
			</li>
			<li aria-current={page.url.pathname === '/conclusion' ? 'page' : undefined}>
				<a href={resolve('/conclusion')}>Conclusion</a>
			</li>
		</ul>
	</nav>
</header>

<style>
	header {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 1rem;
		background: rgba(10, 10, 30, 0.9);
		border-bottom: 1px solid rgba(0, 212, 255, 0.3);
		backdrop-filter: blur(10px);
		position: sticky;
		top: 0;
		z-index: 100;
	}

	.logo {
		margin-bottom: 1rem;
	}

	.logo a {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		text-decoration: none;
	}

	.logo-icon {
		font-size: 2rem;
		animation: pulse 2s infinite;
	}

	.logo-text {
		font-size: 1.5rem;
		font-weight: 700;
		background: linear-gradient(90deg, #00d4ff, #a855f7);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-clip: text;
	}

	@keyframes pulse {
		0%, 100% { opacity: 1; }
		50% { opacity: 0.5; }
	}

	nav ul {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		gap: 0.25rem;
		padding: 0;
		margin: 0;
		list-style: none;
	}

	nav li {
		padding: 0;
	}

	nav li::before {
		content: none;
	}

	nav a {
		display: block;
		padding: 0.5rem 0.75rem;
		color: rgba(240, 248, 255, 0.8);
		font-size: 0.85rem;
		font-weight: 500;
		text-decoration: none;
		border-radius: 6px;
		transition: all 0.3s ease;
	}

	nav a:hover {
		color: #00d4ff;
		background: rgba(0, 212, 255, 0.1);
	}

	nav li[aria-current='page'] a {
		color: #00d4ff;
		background: rgba(0, 212, 255, 0.15);
		border: 1px solid rgba(0, 212, 255, 0.3);
	}

	@media (min-width: 768px) {
		header {
			flex-direction: row;
			justify-content: space-between;
		}

		.logo {
			margin-bottom: 0;
		}

		nav ul {
			gap: 0.5rem;
		}

		nav a {
			font-size: 0.9rem;
		}
	}
</style>
