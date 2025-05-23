<script lang="ts">
	const characterInfo = {
		name: "GLEB STRIZHAK",
		title: "Full-Stack Developer",
		level: 24,
		race: "Developer",
		class: "Full-Stack Mage",
		birthsign: "The Coder",
		attributes: [
			{ name: "Problem Solving", value: 95 },
			{ name: "Creativity", value: 88 },
			{ name: "Communication", value: 82 },
			{ name: "Leadership", value: 75 }
		],
		background: `Developer with an experience of creating immersive digital design.<br>
Skilled in the ancient arts of web development and modern frameworks.<br>
Seeking to forge powerful applications and contribute to meaningful projects.`
	};
</script>

<div class="character-screen">
	<div class="character-sheet">
		<div class="header">
			<h1>{characterInfo.name}</h1>
			<p class="title">{characterInfo.title}</p>
		</div>

		<div class="stats-grid">
			<div class="stat-box">
				<h2>LEVEL</h2>
				<p>{characterInfo.level}</p>
			</div>
			<div class="stat-box">
				<h2>RACE</h2>
				<p>{characterInfo.race}</p>
			</div>
			<div class="stat-box">
				<h2>CLASS</h2>
				<p>{characterInfo.class}</p>
			</div>
			<div class="stat-box">
				<h2>BIRTHSIGN</h2>
				<p>{characterInfo.birthsign}</p>
			</div>
		</div>

		<div class="attributes">
			<h2>ATTRIBUTES</h2>
			{#each characterInfo.attributes as attr}
				<div class="attribute">
					<span class="attr-name">{attr.name}</span>
					<div class="attr-bar-container">
						<div class="attr-bar" style="width: {attr.value}%"></div>
					</div>
					<span class="attr-value">{attr.value}</span>
				</div>
			{/each}
		</div>

		<div class="background">
			<h2>BACKGROUND</h2>
				<p>{@html characterInfo.background}</p>
		</div>
	</div>
</div>

<style>
	:global(main) {
		width: 100%;
		height: 100vh;
		margin: 0;
		padding: 0;
		overflow-x: hidden;
		position: relative;
		scrollbar-width: none;  /* Firefox */
		-ms-overflow-style: none;  /* IE and Edge */
	}

	:global(main::-webkit-scrollbar) {
		display: none;  /* Chrome, Safari and Opera */
	}

	.character-screen {
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		padding: 1rem;
		display: flex;
		width: 100%;
		min-height: 100vh;
		justify-content: center;
		align-items: flex-start;
		box-sizing: border-box;
		overflow-x: hidden;
		scrollbar-width: none;
		-ms-overflow-style: none;
	}

	.character-screen::-webkit-scrollbar {
		display: none;
	}

	.character-sheet {
		position: relative;
		background-image: url('/images/ui/Vector 4.svg');
		background-repeat: no-repeat;
		background-position: center;
		background-size: contain;
		width: 100%;
		max-width: 1200px;
		height: 100%;
		min-height: 800px;
		padding: 3rem;
		display: flex;
		flex-direction: column;
		margin-top: 0;
	}

	.header {
		text-align: center;
		margin-bottom: 2rem;
	}

	.header h1 {
		color: #E0D3B8;
		font-size: 2.5rem;
		margin: 0;
		text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
	}

	.title {
		color: #9C7C38;
		font-size: 1.2rem;
		margin: 0.5rem 0 0 0;
	}

	.stats-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
		gap: 1rem;
		margin-bottom: 2rem;
	}

	.stat-box {
		text-align: center;
	}

	.stat-box h2 {
		color: #9C7C38;
		font-size: 1rem;
		margin: 0 0 0.5rem 0;
	}

	.stat-box p {
		color: #E0D3B8;
		font-size: 1.2rem;
		margin: 0;
	}

	.attributes {
		margin-bottom: 2rem;
	}

	.attributes h2 {
		color: #E0D3B8;
		font-size: 1.8rem;
		margin: 0 0 1rem 0;
		border-bottom: 1px solid #644D25;
		padding-bottom: 0.5rem;
	}

	.attribute {
		display: grid;
		grid-template-columns: 150px 1fr 50px;
		gap: 1rem;
		align-items: center;
		margin-bottom: 0.5rem;
	}

	.attr-name {
		color: #E0D3B8;
	}

	.attr-bar-container {
		height: 8px;
		background: rgba(156, 124, 56, 0.3);
	}

	.attr-bar {
		height: 100%;
		background: #9C7C38;
		transition: width 0.3s ease;
	}

	.attr-value {
		color: #E0D3B8;
		text-align: right;
	}

	.background {
		margin-top: 2rem;
	}

	.background h2 {
		color: #E0D3B8;
		font-size: 1.8rem;
		margin: 0 0 1rem 0;
		border-bottom: 1px solid #644D25;
		padding-bottom: 0.5rem;
	}

	.background p {
		color: #E0D3B8;
		line-height: 1.6;
		margin: 0;
	}

	@media (max-width: 1024px) {
		.character-sheet {
			min-height: auto;
			padding: 2rem;
			background-image: none;
		}
	}
</style>
