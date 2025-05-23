<script lang="ts">
	const projects = [
		{
			title: "Ancient Artifact",
			description: "A powerful web application crafted with modern technologies to achive success.",
			status: "Completed",
			technologies: ["Next", "Typescript", "Three.js"],
			link: "https://ryanjacob.info/"
		},
		{
			title: "Magical Scroll",
			description: "AMAZON Scraper that opens a portal to various wonders.",
			status: "Completed",
			technologies: ["Typescript", "Crawlee", "Apify"],
			link: "https://apify.com/16redflags/amazon-scraper"
		},
		{
			title: "Dragon's Database",
			description: "A robust PC Building database management system with powerful features.",
			status: "In Progress",
			technologies: ["PostgreSQL", "Next", "TypeScript"],
			link: "https://github.com/yourusername/project3"
		}
	];
</script>

<div class="quest-log">
	<div class="quest-header">
		<h1>QUEST LOG</h1>
		<div class="quest-count">COMPLETED QUESTS: {projects.length}</div>
	</div>
	
	<div class="quests">
		{#each projects as project}
			<div class="quest-item">
				<div class="quest-title">
					<img src="/images/ui/arrow.svg" alt="" class="marker" />
					<h2>{project.title}</h2>
					<span class="quest-status {project.status.toLowerCase()}">{project.status}</span>
				</div>
				
				<p class="quest-description">{project.description}</p>
				
				<div class="quest-details">
					<div class="technologies">
						<h3>SKILLS REQUIRED</h3>
						<ul>
							{#each project.technologies as tech}
								<li>{tech}</li>
							{/each}
						</ul>
					</div>
					
					<a href={project.link} class="skyrim-button" target="_blank" rel="noopener">
						VIEW DETAILS
					</a>
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
	:global(main) {
		width: 100%;
		margin: 0;
		display: flex;
		justify-content: center;
		padding: 0;
		overflow-x: hidden;
	}
	.quest-log {
		padding: 2rem;
		width: 100%;
		max-width: 1600px;
		min-height: 900px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	.quest-header {
		text-align: center;
		margin-bottom: 3rem;
	}

	h1 {
		color: var(--color-primary);
		font-size: 3rem;
		margin-bottom: 0.5rem;
		text-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
	}

	.quest-count {
		color: var(--color-secondary);
		font-size: 1.2rem;
		letter-spacing: 2px;
	}

	.quests {
		display: flex;
		flex-wrap: wrap;
		gap: 1.5rem;
		justify-content: center;
	}

	.quest-item {
		flex: 1 1 300px;
		max-width: 400px;
		background: var(--color-bg-0);
		border: 1px solid var(--color-border);
		padding: 1.5rem;
	}

	@media (max-width: 1024px) {
		.quests {
			flex-direction: column;
			align-items: center;
		}

		.quest-item {
			flex: none;
			width: 100%;
			max-width: 600px;
		}
	}

	.quest-title {
		display: flex;
		align-items: center;
		gap: 1rem;
		margin-bottom: 1rem;
	}

	.marker {
		width: 20px;
		height: 20px;
		object-fit: contain;
	}

	.quest-title h2 {
		color: var(--color-primary);
		font-size: 1.5rem;
		margin: 0;
		flex-grow: 1;
	}

	.quest-status {
		font-size: 0.9rem;
		color: var(--color-secondary);
		letter-spacing: 1px;
	}

	.quest-status.completed {
		color: var(--color-accent);
	}

	.quest-description {
		color: var(--color-secondary);
		margin: 1rem 0;
		line-height: 1.6;
		font-size: 1.1rem;
	}

	.quest-details {
		display: flex;
		justify-content: space-between;
		align-items: flex-end;
		margin-top: 1.5rem;
		padding-top: 1rem;
		border-top: 1px solid var(--color-border);
	}

	.technologies h3 {
		color: var(--color-primary);
		font-size: 1rem;
		margin-bottom: 0.5rem;
	}

	.technologies ul {
		list-style: none;
		padding: 0;
		margin: 0;
		display: flex;
		gap: 1rem;
		flex-wrap: wrap;
	}

	.technologies li {
		color: var(--color-secondary);
		font-size: 1rem;
	}

	.technologies li::before {
		content: "•";
		color: var(--color-accent);
		margin-right: 0.5rem;
	}
</style>
