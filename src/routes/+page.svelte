<script>
	import DiamondLattice from '$lib/DiamondLattice.svelte';

	const cast = [
		'Roxzane T. Mims',
		'Ohaji Williams',
		'Elle Trapkin',
		'Angel L. Henderson',
		'Pamela Lyles',
		'Auburn Chandler',
		'Jovan Johnson'
	];
</script>

<svelte:head>
	<title>Short Term — A Crucial Werks Film</title>
	<meta name="description" content="Some people never really leave. Short Term — written and directed by John Russel. A Crucial Werks Film." />
</svelte:head>

<!-- HERO -->
<section class="hero">
	<div class="hero-bg">
		<img src="/poster.jpg" alt="Short Term movie poster" class="poster-img" />
		<div class="poster-vignette" />
	</div>

	<DiamondLattice></DiamondLattice>

	<div class="hero-content">
		<p class="studio">A Crucial Werks Film</p>
		<h1 class="title">Short<br />Term</h1>
		<p class="tagline">Some people never really leave.</p>
	</div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
	<div class="about-inner">
		<div class="diamond-rule" aria-hidden="true">
			<span class="rule-line"></span>
			<span class="rule-diamond">◆</span>
			<span class="rule-line"></span>
		</div>
		<p class="synopsis">
			<em>Short Term</em> is a psychological drama exploring the haunting grip of the past on the present — where the walls of a transitional facility hold secrets that refuse to stay buried.
		</p>
	</div>
</section>

<!-- CAST & CREW -->
<section class="credits" id="credits">
	<div class="credits-inner">
		<h2 class="section-label">Cast</h2>
		<ul class="cast-list">
			{#each cast as name}
				<li>{name}</li>
			{/each}
		</ul>

		<div class="crew-block">
			<div class="crew-row">
				<span class="crew-role">Written &amp; Directed by</span>
				<span class="crew-name">John Russel</span>
			</div>
			<div class="crew-row">
				<span class="crew-role">Director of Photography</span>
				<span class="crew-name">Darius J. Thompson</span>
			</div>
			<div class="crew-row">
				<span class="crew-role">Production Designer</span>
				<span class="crew-name">Miles B. Carter</span>
			</div>
			<div class="crew-row">
				<span class="crew-role">Edited by</span>
				<span class="crew-name">John Russell</span>
			</div>
			<div class="crew-row">
				<span class="crew-role">Executive Producer</span>
				<span class="crew-name">John Russel</span>
			</div>
		</div>
	</div>
</section>

<!-- FOOTER -->
<footer class="footer">
	<p class="footer-studio">Crucial Werks Productions</p>
	<p class="footer-copy">&copy; {new Date().getFullYear()} Crucial Werks. All rights reserved.</p>
</footer>

<style>
	/* ── HERO ── */
	.hero {
		position: relative;
		width: 100%;
		height: 100svh;
		min-height: 600px;
		overflow: hidden;
		display: flex;
		align-items: flex-end;
	}

	.hero-bg {
		position: absolute;
		inset: 0;
		z-index: 0;
	}

	.poster-img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		object-position: center top;
		display: block;
	}

	.poster-vignette {
		position: absolute;
		inset: 0;
		background: linear-gradient(
			to bottom,
			rgba(10, 12, 16, 0.15) 0%,
			rgba(10, 12, 16, 0) 30%,
			rgba(10, 12, 16, 0.4) 60%,
			rgba(10, 12, 16, 0.92) 100%
		);
	}

	.hero-content {
		position: relative;
		z-index: 10;
		padding: 0 clamp(1.5rem, 5vw, 5rem) clamp(3rem, 8vh, 6rem);
		pointer-events: none;
	}

	.studio {
		font-family: 'Montserrat', sans-serif;
		font-size: clamp(0.6rem, 1.2vw, 0.75rem);
		font-weight: 400;
		letter-spacing: 0.35em;
		text-transform: uppercase;
		color: #a09890;
		margin-bottom: 0.75rem;
	}

	.title {
		font-family: 'Cormorant Garamond', serif;
		font-size: clamp(4rem, 12vw, 9rem);
		font-weight: 300;
		line-height: 0.9;
		letter-spacing: 0.06em;
		color: #f0ece4;
		text-transform: uppercase;
		margin-bottom: 1.25rem;
	}

	.tagline {
		font-family: 'Montserrat', sans-serif;
		font-size: clamp(0.7rem, 1.5vw, 0.9rem);
		font-weight: 300;
		letter-spacing: 0.25em;
		text-transform: uppercase;
		color: #c8c0b4;
	}

	/* ── ABOUT ── */
	.about {
		padding: clamp(4rem, 10vh, 7rem) clamp(1.5rem, 5vw, 5rem);
		background: #0a0c10;
	}

	.about-inner {
		max-width: 680px;
		margin: 0 auto;
		text-align: center;
	}

	.diamond-rule {
		display: flex;
		align-items: center;
		gap: 1rem;
		margin-bottom: 2.5rem;
	}

	.rule-line {
		flex: 1;
		height: 1px;
		background: linear-gradient(to right, transparent, #4a4540);
	}

	.rule-line:last-child {
		background: linear-gradient(to left, transparent, #4a4540);
	}

	.rule-diamond {
		color: #6b5f52;
		font-size: 0.55rem;
	}

	.synopsis {
		font-size: clamp(0.95rem, 2vw, 1.15rem);
		line-height: 1.85;
		color: #b0a898;
		font-weight: 300;
		letter-spacing: 0.02em;
	}

	.synopsis em {
		font-style: italic;
		color: #d4cfc8;
	}

	/* ── CREDITS ── */
	.credits {
		padding: clamp(3rem, 8vh, 5rem) clamp(1.5rem, 5vw, 5rem) clamp(4rem, 10vh, 7rem);
		background: #080a0d;
		border-top: 1px solid #1a1c20;
	}

	.credits-inner {
		max-width: 680px;
		margin: 0 auto;
	}

	.section-label {
		font-family: 'Montserrat', sans-serif;
		font-size: 0.65rem;
		font-weight: 600;
		letter-spacing: 0.4em;
		text-transform: uppercase;
		color: #5a5248;
		margin-bottom: 1.5rem;
	}

	.cast-list {
		list-style: none;
		display: flex;
		flex-wrap: wrap;
		gap: 0.4rem 0;
		margin-bottom: 3.5rem;
	}

	.cast-list li {
		font-size: clamp(0.85rem, 1.8vw, 1rem);
		color: #c8c0b4;
		letter-spacing: 0.08em;
		font-weight: 300;
		width: 100%;
	}

	.cast-list li::before {
		content: '◆';
		font-size: 0.4rem;
		color: #5a5248;
		margin-right: 0.75rem;
		vertical-align: middle;
	}

	.crew-block {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		border-top: 1px solid #1a1c20;
		padding-top: 2rem;
	}

	.crew-row {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		gap: 1rem;
	}

	.crew-role {
		font-size: 0.65rem;
		letter-spacing: 0.25em;
		text-transform: uppercase;
		color: #5a5248;
		flex-shrink: 0;
	}

	.crew-name {
		font-size: 0.9rem;
		letter-spacing: 0.1em;
		color: #c8c0b4;
		text-align: right;
	}

	/* ── FOOTER ── */
	.footer {
		padding: 2rem clamp(1.5rem, 5vw, 5rem);
		background: #060708;
		border-top: 1px solid #12141a;
		text-align: center;
	}

	.footer-studio {
		font-size: 0.7rem;
		letter-spacing: 0.35em;
		text-transform: uppercase;
		color: #4a4540;
		margin-bottom: 0.5rem;
	}

	.footer-copy {
		font-size: 0.65rem;
		letter-spacing: 0.1em;
		color: #2e2c28;
	}

	/* ── RESPONSIVE ── */
	@media (min-width: 768px) {
		.cast-list {
			display: grid;
			grid-template-columns: 1fr 1fr;
			gap: 0.5rem 2rem;
		}

		.cast-list li {
			width: auto;
		}
	}
</style>
