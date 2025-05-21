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
		min-height: 60px;
		display: flex;
		align-items: center;
	}

	.header-bg::before {
		content: '';
		position: absolute;
		top: 0;
		left: 50%;
		width: 1200px;
		transform: translateX(-50%);
		bottom: 0;
		box-shadow: inset 0 100px 10px rgba(0, 0, 0, 0.3);
		pointer-events: none;
		border-radius: 30px;
	}

	nav {
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		display: flex;
		justify-content: center;
	}

	ul {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		list-style: none;
		margin: 0;
		padding: 0;
	}

	li {
		position: relative;
		padding: 0.25rem 1rem;
		transition: all 0.3s ease;
		display: flex;
		align-items: center;
		gap: 0.5rem;
	}

	.marker {
		width: 16px;
		height: 16px;
		opacity: 0;
		transition: opacity 0.3s ease;
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
		font-size: 1rem;
		transition: color 0.3s ease;
		text-align: center;
		min-width: 150px;
	}

	li.active a {
		color: #5c471f;
	}

	@media (min-width: 768px) {
		ul {
			flex-direction: row;
			gap: 2rem;
		}
	}
</style>
