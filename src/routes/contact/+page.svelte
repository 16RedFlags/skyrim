<script lang="ts">
	function openGitHub() {
		window.open('https://github.com/16RedFlags', '_blank');
	}
</script>

<div class="contact-container">
	<h1>Contact</h1>
	<p class="contact-email">Email: <a href="mailto:geradotus022@gmail.com">geradotus022@gmail.com</a></p>
	<button class="github-btn" on:click={openGitHub}>
		<img src="/images/github-mark.svg" alt="GitHub" />
		GitHub
	</button>
</div>

<style>
.contact-container {
	max-width: 400px;
	margin: 4rem auto;
	background: rgba(0,0,0,0.85);
	border: 2px solid #5B5B5B;
	padding: 2rem;
	border-radius: 12px;
	text-align: center;
}
.contact-email {
	color: #E0D3B8;
	font-size: 1.1rem;
	margin-bottom: 2rem;
	word-break: break-all;
}
.contact-email a {
	color: #E0D3B8;
	text-decoration: none;
	cursor: url('/images/cursors/Skyrim-normal.cur'), auto;
}
.github-btn {
	display: flex;
	align-items: center;
	gap: 0.5rem;
	background: transparent;
	color: #E0D3B8;
	border: 1px solid #644D25;
	padding: 0.7rem 1.5rem;
	border-radius: 4px;
	font-size: 1rem;
	cursor: url('/images/cursors/Skyrim-normal.cur'), auto;
	transition: background 0.2s, color 0.2s;
	margin: 0 auto;
}
.github-btn img {
	width: 24px;
	height: 24px;
}
.github-btn:hover {
	background: #644D25;
	color: #fff;
}
</style>
