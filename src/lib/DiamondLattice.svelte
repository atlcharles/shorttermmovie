<script>
	import { onMount } from 'svelte';

	// Diamond cell size in px
	const W = 130;
	const H = 130;
	// Offset for interlocking rows
	const rowH = H / 2;
	const colW = W;

	/** @type {HTMLDivElement} */
	let container;
	/** @type {{ id: number; x: number; y: number; row: number }[]} */
	let diamonds = $state([]);

	onMount(() => {
		const { offsetWidth: vw, offsetHeight: vh } = container;
		// Extra cells to bleed off-screen edges
		const cols = Math.ceil(vw / colW) + 2;
		const rows = Math.ceil(vh / rowH) + 2;
		const cells = [];
		let id = 0;
		for (let r = -1; r < rows; r++) {
			for (let c = -1; c < cols; c++) {
				const offset = r % 2 === 0 ? 0 : W / 2;
				cells.push({ id: id++, x: c * colW + offset - W / 2, y: r * rowH - H / 2, row: r });
			}
		}
		diamonds = cells;
	});
</script>

<div class="lattice" bind:this={container} aria-hidden="true">
	{#each diamonds as d (d.id)}
		<div
			class="diamond"
			style="left:{d.x}px; top:{d.y}px; width:{W}px; height:{H}px;"
		></div>
	{/each}
</div>

<style>
	.lattice {
		position: absolute;
		inset: 0;
		z-index: 5;
		pointer-events: none;
		overflow: hidden;
	}

	/* Re-enable pointer events on individual diamonds */
	.diamond {
		pointer-events: auto;
		position: absolute;
		clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
		/* Base: frosted/darkened pane */
		background: rgba(10, 12, 16, 0.38);
		backdrop-filter: blur(3px) brightness(0.75) saturate(0.7);
		-webkit-backdrop-filter: blur(3px) brightness(0.75) saturate(0.7);
		transition:
			backdrop-filter 0.55s cubic-bezier(0.25, 0.46, 0.45, 0.94),
			-webkit-backdrop-filter 0.55s cubic-bezier(0.25, 0.46, 0.45, 0.94),
			background 0.55s ease;
		cursor: default;
	}

	.diamond:hover {
		background: rgba(10, 12, 16, 0.04);
		backdrop-filter: blur(0px) brightness(1.08) saturate(1.15);
		-webkit-backdrop-filter: blur(0px) brightness(1.08) saturate(1.15);
		transition:
			backdrop-filter 0.2s cubic-bezier(0.25, 0.46, 0.45, 0.94),
			-webkit-backdrop-filter 0.2s cubic-bezier(0.25, 0.46, 0.45, 0.94),
			background 0.2s ease;
	}

	/*
	 * The "lines" between diamonds are just the background showing through
	 * the gaps between clip-path polygons — no extra elements needed.
	 * The gap width is controlled by the cell sizing (W, H) vs the polygon.
	 * Since adjacent diamonds share edges at 50% points, overlapping them
	 * slightly reveals a thin dark seam naturally.
	 */
</style>
