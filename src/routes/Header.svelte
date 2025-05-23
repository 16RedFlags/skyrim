<script lang="ts">
	import { page } from '$app/stores';
	import { onMount } from 'svelte';

	let categories = [
		{ id: 'about', name: 'PROFILE', href: '/about' },
		{ id: 'skills', name: 'SKILLS & PERKS', href: '/skills' },
		{ id: 'projects', name: 'QUESTS COMPLETED', href: '/projects' },
		{ id: 'contact', name: 'CONTACT', href: '/contact' }
	];

	let activeCategory = categories[0];

	// Set activeCategory based on current path
	$: {
		const currentPath = $page.url.pathname;
		const found = categories.find(cat => currentPath.startsWith(cat.href));
		if (found) activeCategory = found;
	}
</script>

<header>
	<div class="header-bg">
		<nav>
			<ul>
				{#each categories as category}
					<li class:active={activeCategory.id === category.id}>
						<img src="/images/ui/arrow.svg" alt="" class="marker left" class:visible={activeCategory.id === category.id} />
						<a 
							href={category.href}
							on:click={() => activeCategory = category}
						>
							{category.name}
						</a>
						<img src="/images/ui/arrow.svg" alt="" class="marker right" class:visible={activeCategory.id === category.id} />
					</li>
				{/each}
			</ul>
		</nav>
	</div>
</header>

<style>
	header {
		position: relative;
		width: 100%;
		padding: 0.5rem 0;
	}

	.header-bg {
		position: relative;
		background-image: url('/images/ui/header-bg.svg');
		background-repeat: no-repeat;
		background-position: center;
		background-size: contain;
		width: 100%;
		min-height: clamp(40px, 8vw, 60px);
		display: flex;
		align-items: center;
		padding: clamp(0.5rem, 2vw, 1rem) 0;
	}

	nav {
		width: 100%;
		max-width: min(90vw, 1024px);
		margin: 0 auto;
		display: flex;
		justify-content: center;
		padding: 0 clamp(0.5rem, 2vw, 1rem);
	}

	ul {
		display: flex;
		flex-direction: column;
		gap: clamp(0.5rem, 2vw, 1rem);
		list-style: none;
		margin: 0;
		padding: 0;
		width: 100%;
	}

	li {
		position: relative;
		padding: clamp(0.15rem, 1vw, 0.25rem) clamp(0.5rem, 2vw, 1rem);
		transition: all 0.3s ease;
		display: flex;
		align-items: center;
		gap: clamp(0.25rem, 1vw, 0.5rem);
		justify-content: center;
	}

	.marker {
		width: clamp(12px, 2vw, 16px);
		height: clamp(12px, 2vw, 16px);
		opacity: 0;
		transition: opacity 0.3s ease;
		flex-shrink: 0;
	}

	.marker.right {
		transform: rotate(180deg);
	}

	.marker.visible {
		opacity: 1;
	}

	a {
		color: #E0D3B8;
		text-decoration: none;
		font-size: clamp(0.875rem, 2.5vw, 1rem);
		transition: color 0.3s ease;
		text-align: center;
		min-width: clamp(100px, 20vw, 150px);
		white-space: nowrap;
		cursor: url('/images/cursors/Skyrim-normal.cur'), auto;
	}

	li.active a {
		color: #5c471f;
	}

	@media (min-width: 768px) {
		ul {
			flex-direction: row;
			gap: clamp(1rem, 3vw, 2rem);
			justify-content: center;
		}

		nav {
			padding: 0;
		}
	}

	@media (max-width: 1100px) {
		.header-bg {
			background-image: none;
		}
	}

	@media (max-width: 767px) {
		.header-bg {
			padding: clamp(1rem, 4vw, 2rem) 0;
		}
	}
</style>
