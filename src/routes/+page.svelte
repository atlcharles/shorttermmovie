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

	const crew = [
		{ role: 'Written & Directed by', name: 'John Russel' },
		{ role: 'Director of Photography', name: 'Darius J. Thompson' },
		{ role: 'Production Designer', name: 'Miles B. Carter' },
		{ role: 'Executive Producer', name: 'John Russel' }
	];
</script>

<svelte:head>
	<title>Short Term — A Crucial Werks Film</title>
	<meta name="description" content="Some people never really leave. Short Term — written and directed by John Russel. A Crucial Werks Film." />
</svelte:head>

<!-- HERO -->
<section class="hero" aria-label="Short Term film hero">
	<div class="hero-bg">
		<img
			src="/poster.png"
			alt="Three faces seen through diamond-shaped frosted glass window panes — poster for Short Term, a Crucial Werks film"
			class="poster-img"
		/>
		<div class="poster-vignette" aria-hidden="true"></div>
	</div>

	<DiamondLattice></DiamondLattice>

	<div class="hero-content">
		<p class="studio">A Crucial Werks Film</p>
		<h1 class="title">Short<br />Term</h1>
		<p class="tagline">Some people never really leave.</p>
	</div>
</section>

<!-- ABOUT -->
<section class="about" id="about" aria-label="About the film">
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

		<dl class="crew-block">
			{#each crew as { role, name }}
				<div class="crew-row">
					<dt class="crew-role">{role}</dt>
					<dd class="crew-name">{name}</dd>
				</div>
			{/each}
		</dl>
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
		font-size: clamp(0.75rem, 1.4vw, 0.875rem);
		font-weight: 400;
		letter-spacing: 0.15em;
		color: #c0b8b0;
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
		font-size: clamp(0.8rem, 1.6vw, 1rem);
		font-weight: 300;
		letter-spacing: 0.1em;
		color: #d4cec6;
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
		font-size: clamp(1rem, 2vw, 1.15rem);
		line-height: 1.85;
		color: #c0b8b0;
		font-weight: 300;
		letter-spacing: 0.02em;
	}

	.synopsis em {
		font-style: italic;
		color: #dedad4;
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
		font-size: 0.75rem;
		font-weight: 600;
		letter-spacing: 0.2em;
		color: #a09888;
		margin-bottom: 1.5rem;
	}

	.cast-list {
		list-style: none;
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem 0;
		margin-bottom: 3.5rem;
	}

	.cast-list li {
		font-size: clamp(0.9rem, 1.8vw, 1rem);
		color: #d0c8c0;
		letter-spacing: 0.05em;
		font-weight: 300;
		width: 100%;
	}

	.cast-list li::before {
		content: '◆';
		font-size: 0.4rem;
		color: #6b6058;
		margin-right: 0.75rem;
		vertical-align: middle;
	}

	.crew-block {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		border-top: 1px solid #1a1c20;
		padding-top: 2rem;
		margin: 0;
	}

	.crew-row {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		gap: 1rem;
	}

	.crew-role {
		font-size: 0.8rem;
		letter-spacing: 0.08em;
		color: #9a9088;
		flex-shrink: 0;
	}

	.crew-name {
		font-size: 0.95rem;
		letter-spacing: 0.06em;
		color: #d0c8c0;
		text-align: right;
		margin: 0;
	}

	/* ── FOOTER ── */
	.footer {
		padding: 2rem clamp(1.5rem, 5vw, 5rem);
		background: #060708;
		border-top: 1px solid #12141a;
		text-align: center;
	}

	.footer-studio {
		font-size: 0.8rem;
		letter-spacing: 0.15em;
		color: #8a8078;
		margin-bottom: 0.5rem;
	}

	.footer-copy {
		font-size: 0.75rem;
		letter-spacing: 0.05em;
		color: #706860;
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

	/* ── REDUCED MOTION ── */
	@media (prefers-reduced-motion: reduce) {
		:global(.diamond) {
			transition: none !important;
		}
	}
</style>
