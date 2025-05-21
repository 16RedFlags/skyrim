<script lang="ts">
	const skills = [
		{
			name: "Frontend Development",
			level: 85,
			perks: ["JavaScript", "TypeScript", "React", "Svelte", "Next", "Three"]
		},
		{
			name: "Backend Development",
			level: 75,
			perks: ["Node.js", "Express", "PostgreSQL", "MongoDB", "REST APIs"]
		},
		{
			name: "DevOps",
			level: 65,
			perks: ["Git", "Docker", "CI/CD", "AWS", "Linux"]
		},
		{
			name: "UI/UX Design",
			level: 70,
			perks: ["Figma", "Adobe XD", "Responsive Design", "Accessibility"]
		}
	];
</script>

<div class="skills-screen">
	<h1 class="skills-title">SKILLS & PERKS</h1>
	
	<div class="skills-grid">
		{#each skills as skill}
			<div class="skill-card">
				<div class="skill-header">
					<h2>{skill.name}</h2>
					<div class="skill-level">
						<div class="level-bar-bg">
							<div class="level-bar" style="width: {skill.level}%"></div>
						</div>
						<span class="level-number">{skill.level}</span>
					</div>
				</div>
				
				<div class="perks">
					<h3>PERKS</h3>
					<ul>
						{#each skill.perks as perk}
							<li>
								<span class="perk-marker">★</span>
								{perk}
							</li>
						{/each}
					</ul>
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.skills-screen {
		padding: 2rem;
		max-width: 1200px;
		margin: 0 auto;
	}

	.skills-title {
		text-align: center;
		color: #E0D3B8;
		font-size: 2.5rem;
		margin-bottom: 2rem;
		text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
	}

	.skills-grid {
		display: flex;
		flex-wrap: wrap;
		gap: 2rem;
		justify-content: center;
	}

	.skill-card {
		flex: 1 1 300px;
		max-width: 400px;
		background: rgba(0, 0, 0, 0.85);
		border: 2px solid #5B5B5B;
		padding: 1.5rem;
	}

	.skill-header h2 {
		color: #E0D3B8;
		margin: 0 0 1rem 0;
		font-size: 1.5rem;
	}

	.skill-level {
		display: flex;
		align-items: center;
		gap: 1rem;
	}

	.level-bar-bg {
		flex: 1;
		height: 8px;
		background: rgba(156, 124, 56, 0.3);
	}

	.level-bar {
		height: 100%;
		background: #9C7C38;
		transition: width 0.3s ease;
	}

	.level-number {
		color: #9C7C38;
		font-size: 1.2rem;
		min-width: 2.5rem;
	}

	.perks {
		margin-top: 1.5rem;
	}

	.perks h3 {
		color: #9C7C38;
		font-size: 1.2rem;
		margin: 0 0 0.5rem 0;
		border-bottom: 1px solid #644D25;
		padding-bottom: 0.3rem;
	}

	.perks ul {
		list-style: none;
		padding: 0;
		margin: 0;
	}

	.perks li {
		color: #E0D3B8;
		margin: 0.5rem 0;
		display: flex;
		align-items: center;
		gap: 0.5rem;
	}

	.perk-marker {
		color: #9C7C38;
		font-size: 0.8rem;
	}
</style>
