<script lang="ts">
	const mainQuest = {
		title: "THE DEVELOPER'S PATH",
		description: "A skilled adventurer in the realm of web development, seeking to create immersive digital experiences.",
		objectives: [
			"Master the ancient arts of Frontend Development",
			"Craft powerful spells using Modern Frameworks",
			"Create enchanted user experiences",
			"Forge robust backend systems"
		]
	};
</script>

<div class="quest-screen">
	<div class="quest-container">
		<h1 class="quest-title">{mainQuest.title}</h1>
		<p class="quest-description">{mainQuest.description}</p>
		
		<div class="objectives">
			<h2>OBJECTIVES</h2>
			<ul>
				{#each mainQuest.objectives as objective}
					<li class="quest-objective">
						<span class="marker">▶</span>
						{objective}
					</li>
				{/each}
			</ul>
		</div>
	</div>
</div>

<style>
	.quest-screen {
		display: flex;
		justify-content: center;
		align-items: flex-start;
		min-height: 100%;
		padding: 2rem;
	}

	.quest-container {
		background: rgba(0, 0, 0, 0.85);
		border: 2px solid #644D25;
		padding: 2rem;
		width: 100%;
		max-width: 800px;
	}

	.quest-title {
		text-align: center;
		color: #E0D3B8;
		font-size: 2.5rem;
		margin: 0 0 2rem 0;
		text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
	}

	.quest-description {
		font-size: 1.2rem;
		line-height: 1.6;
		color: #9C7C38;
		margin: 0 0 2rem 0;
	}

	.objectives h2 {
		color: #E0D3B8;
		font-size: 1.8rem;
		margin: 0 0 1rem 0;
		border-bottom: 2px solid #644D25;
		padding-bottom: 0.5rem;
	}

	.objectives ul {
		list-style: none;
		padding: 0;
		margin: 0;
	}

	.quest-objective {
		color: #E0D3B8;
		font-size: 1.1rem;
		margin: 0.5rem 0;
		display: flex;
		align-items: center;
		gap: 0.5rem;
	}

	.marker {
		color: #9C7C38;
		font-size: 0.8rem;
	}
</style>
