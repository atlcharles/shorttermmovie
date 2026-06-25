<script>
	import DiamondLattice from '$lib/DiamondLattice.svelte';

	const cast = [
		{ actor: 'Roxzane T. Mims', character: 'Angelica Mason' },
		{ actor: 'Ohaji Williams', character: 'Ethan' },
		{ actor: 'Elle Trapkin', character: 'Dr. Wixom' },
		{ actor: 'Nic Starr', character: 'Thomas' },
		{ actor: 'Angel L. Henderson', character: 'Wendy' },
		{ actor: 'Pamela Lyles', character: 'Lisa' },
		{ actor: 'Auburn Chandler', character: 'Officer Nickels' },
		{ actor: 'Jovan Johnson', character: 'Officer Randell' }
	];

	const crew = [
		{ role: 'Writer, Director', name: 'John Russel' },
		{ role: 'Producer', name: 'John Russel, Jordan Marcel' },
		{ role: 'Executive Producer', name: 'Misha Broughton' },
		{ role: 'Associate Producer', name: 'Tamera Miyasato' },
		{ role: 'Director of Photography', name: 'Jordan Marcel' },
		{ role: 'Editor', name: 'Jordan Marcel' },
		{ role: 'Boom Operator, Sound Mixer', name: 'Zach Shoup' },
		{ role: 'Hair & Makeup', name: 'Karmen Russell' },
		{ role: 'Costume Design', name: 'Summer Tinch' },
		{ role: 'Physical and Post Production', name: 'Southeast Cinema' }
	];
</script>

<svelte:head>
	<title>Short Term — A John Russel Film</title>
	<meta name="description" content="A grieving widow rents a room to a charming travel nurse, only to become convinced he may be the killer she has been hearing about on the news. Short Term — written and directed by John Russel. A Crucial Werks production." />
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
		<div class="social-links">
			<a href="https://www.instagram.com/shorttermmovie" target="_blank" rel="noopener noreferrer" aria-label="Instagram">
				<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="social-icon" width="22" height="22">
					<defs>
						<radialGradient id="ig-grad" r="150%" cx="30%" cy="107%">
							<stop offset="0%" stop-color="#fdf497"/>
							<stop offset="5%" stop-color="#fdf497"/>
							<stop offset="45%" stop-color="#fd5949"/>
							<stop offset="60%" stop-color="#d6249f"/>
							<stop offset="90%" stop-color="#285AEB"/>
						</radialGradient>
					</defs>
					<rect width="24" height="24" rx="5.5" fill="url(#ig-grad)"/>
					<rect x="2.4" y="2.4" width="19.2" height="19.2" rx="4.2" fill="url(#ig-grad)"/>
					<circle cx="12" cy="12" r="4.2" fill="none" stroke="white" stroke-width="1.8"/>
					<circle cx="17.2" cy="6.8" r="1.1" fill="white"/>
					<rect x="3.5" y="3.5" width="17" height="17" rx="3.5" fill="none" stroke="white" stroke-width="1.5"/>
				</svg>
			</a>
			<a href="https://www.facebook.com/profile.php?id=61590637656028" target="_blank" rel="noopener noreferrer" aria-label="Facebook">
				<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="social-icon" width="22" height="22">
					<rect width="24" height="24" rx="5.5" fill="#1877F2"/>
					<path d="M16 8h-2a1 1 0 0 0-1 1v2h3l-.5 3H13v7h-3v-7H8v-3h2V9a4 4 0 0 1 4-4h2v3z" fill="white"/>
				</svg>
			</a>
		</div>
		<p class="studio">A John Russel Film</p>
		<h1 class="title">Short<br />Term</h1>
		<p class="tagline">Some people never really leave.</p>
	</div>
</section>

<!-- LOGLINE -->
<section class="logline-section" aria-label="Film logline">
	<div class="about-inner">
		<div class="diamond-rule" aria-hidden="true">
			<span class="rule-line"></span>
			<span class="rule-diamond">◆</span>
			<span class="rule-line"></span>
		</div>
		<p class="logline">
			A grieving widow rents a room to a charming travel nurse, only to become convinced he may be the killer she has been hearing about on the news — turning her home into a battleground of fear, memory, and control.
		</p>
	</div>
</section>

<!-- ABOUT THE FILM -->
<section class="about" id="about" aria-label="About the film">
	<div class="about-inner">
		<h2 class="section-label about-label">About the Film</h2>
		<p class="synopsis">
			<em>Short Term</em> is a psychological thriller about grief, manipulation, and the terrifying question of whether the danger outside the house is worse than the truth hiding inside it. Set primarily in one home, the film follows Angelica Mason, a widow whose attempt to survive loneliness pulls her into a deadly psychological spiral.
		</p>
		<p class="synopsis synopsis-second">
			The title carries a double meaning: a short-term stay, and the unraveling of short-term memory.
		</p>
	</div>
</section>

<!-- CAST & CREW -->
<section class="credits" id="credits">
	<div class="credits-inner">
		<h2 class="section-label">Cast</h2>
		<ul class="cast-list">
			{#each cast as { actor, character }}
				<li class="cast-item">
					<span class="cast-actor">{actor}</span>
					<span class="cast-character">{character}</span>
				</li>
			{/each}
		</ul>

		<h2 class="section-label">Crew</h2>

		<dl class="crew-block">
			{#each crew as { role, name }}
				<div class="crew-row">
					<dt class="crew-role">{role}</dt>
					<dd class="crew-name">{name}</dd>
				</div>
			{/each}
		</dl>

		<p class="production-note">A Crucial Werks production in association with Southeast Cinema.</p>
	</div>
</section>

<!-- FOOTER -->
<footer class="footer">
	<a href="https://crucialwerks.com" target="_blank" rel="noopener noreferrer">
		<img src="/cw-noname.jpeg" alt="Crucial Werks logo" class="footer-logo" />
	</a>
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

	/* ── LOGLINE ── */
	.logline-section {
		padding: clamp(4rem, 10vh, 7rem) clamp(1.5rem, 5vw, 5rem);
		background: #0a0c10;
	}

	.logline {
		font-family: 'Cormorant Garamond', serif;
		font-size: clamp(1.1rem, 2.2vw, 1.35rem);
		line-height: 1.75;
		color: #d8d2c8;
		font-weight: 300;
		font-style: italic;
		letter-spacing: 0.02em;
	}

	/* ── ABOUT ── */
	.about {
		padding: clamp(3rem, 7vh, 5rem) clamp(1.5rem, 5vw, 5rem);
		background: #0a0c10;
		border-top: 1px solid #161820;
	}

	.about-inner {
		max-width: 680px;
		margin: 0 auto;
		text-align: center;
	}

	.about-label {
		margin-bottom: 2rem;
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

	.synopsis-second {
		margin-top: 1.5rem;
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
		text-transform: uppercase;
	}

	.cast-list {
		list-style: none;
		display: flex;
		flex-direction: column;
		gap: 0;
		margin-bottom: 3.5rem;
	}

	.cast-item {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		gap: 1rem;
		padding: 0.45rem 0;
		border-bottom: 1px solid #13151a;
	}

	.cast-item:first-child {
		border-top: 1px solid #13151a;
	}

	.cast-actor {
		font-size: clamp(0.9rem, 1.8vw, 1rem);
		color: #d0c8c0;
		letter-spacing: 0.05em;
		font-weight: 300;
	}

	.cast-character {
		font-size: clamp(0.8rem, 1.6vw, 0.9rem);
		color: #8a8078;
		letter-spacing: 0.08em;
		font-style: italic;
		text-align: right;
	}

	.crew-header {
		border-top: 1px solid #1a1c20;
		padding-top: 2rem;
		margin-bottom: 1.5rem;
	}

	.film-credit {
		font-family: 'Cormorant Garamond', serif;
		font-size: clamp(1rem, 2vw, 1.15rem);
		font-style: italic;
		letter-spacing: 0.06em;
		color: #c8c0b4;
		margin: 0;
	}

	.crew-block {
		display: flex;
		flex-direction: column;
		gap: 1rem;
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

	.production-note {
		margin-top: 2.5rem;
		font-size: 0.8rem;
		letter-spacing: 0.08em;
		color: #7a7268;
		font-style: italic;
		text-align: center;
	}

	/* ── FOOTER ── */
	.footer-logo {
		width: auto;
		height: 56px;
		object-fit: contain;
		opacity: 0.85;
		mix-blend-mode: lighten;
		margin-bottom: 1rem;
	}

	.footer {
		padding: 2rem clamp(1.5rem, 5vw, 5rem);
		background: #060708;
		border-top: 1px solid #12141a;
		text-align: center;
	}

	.social-links {
		display: flex;
		justify-content: flex-start;
		gap: 0.75rem;
		margin-bottom: 1.25rem;
	}

	.social-links a {
		display: flex;
		align-items: center;
		opacity: 0.85;
		transition: opacity 0.2s ease;
		pointer-events: all;
	}

	.social-links a:hover {
		opacity: 1;
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
			gap: 0;
		}

		.cast-item {
			padding: 0.5rem 0.75rem;
		}

		.cast-item:nth-child(odd) {
			border-right: 1px solid #13151a;
			padding-left: 0;
		}

		.cast-item:nth-child(even) {
			padding-right: 0;
		}

		.cast-item:first-child,
		.cast-item:nth-child(2) {
			border-top: 1px solid #13151a;
		}
	}

	/* ── REDUCED MOTION ── */
	@media (prefers-reduced-motion: reduce) {
		:global(.diamond) {
			transition: none !important;
		}
	}
</style>
