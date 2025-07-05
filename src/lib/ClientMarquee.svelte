<script>
	import { onMount, onDestroy } from 'svelte';

	let clients = [
		{ src: '/client1.webp', alt: 'Client 1' },
		{ src: '/client2.webp', alt: 'Client 2' },
		{ src: '/client3.webp', alt: 'Client 3' },
		{ src: '/client4.webp', alt: 'Client 4' },
		{ src: '/client5.webp', alt: 'Client 5' },
		{ src: '/client6.webp', alt: 'Client 6' },
		{ src: '/client7.webp', alt: 'Client 7' },
		{ src: '/client8.webp', alt: 'Client 8' },
		{ src: '/client9.webp', alt: 'Client 9' },
		{ src: '/client10.webp', alt: 'Client 10' },
		{ src: '/client11.webp', alt: 'Client 11' },
		{ src: '/client12.webp', alt: 'Client 12' }
	];

	let container;
	let track;
	let speed = $state(60);
	let pos = $state(0);
	let start = $state(null);
	let rafId;
	let trackWidth = $state(0);

	function animate(timestamp) {
		if (!start) start = timestamp;

		const elapsed = timestamp - start;
		pos = -(elapsed / 1000) * speed;

		if (Math.abs(pos) >= trackWidth) {
			start = timestamp;
			pos = 0;
		}

		container.style.transform = `translateX(${pos}px)`;
		rafId = requestAnimationFrame(animate);
	}

	onMount(() => {
		if (typeof window !== 'undefined') {
			trackWidth = track.getBoundingClientRect().width;
			container.style.width = `${trackWidth}px`;
			rafId = requestAnimationFrame(animate);
		}
	});

	onDestroy(() => {
		if (typeof window !== 'undefined') {
			cancelAnimationFrame(rafId);
			if (container) container.style.transform = '';
		}
	});
</script>

<section class="container">
	<!-- <div class="title">
		<span> Our Clients </span>
	</div> -->
	<div class="wrapper">
		<div class="marquee">
			<div bind:this={container} class="marquee-container">
				<div bind:this={track} class="marquee-track">
					{#each clients as { src, alt }}
						<div class="marquee-item">
							<img {src} {alt} />
						</div>
					{/each}
				</div>
				<!-- duplicate for looping effect -->
				<div class="marquee-track" aria-hidden="true">
					{#each clients as { src, alt }}
						<div class="marquee-item">
							<img {src} {alt} />
						</div>
					{/each}
				</div>
			</div>
		</div>
	</div>
</section>

<style lang="scss">
	.container {
		padding: 3rem;
		position: relative;

		display: flex;
		gap: 1rem;
		align-items: center;
	}

	.title {
		color: #fff;
		text-align: center;
		padding: 1rem 1rem 2rem;
		width: 400px;
		span {
			font-size: 2rem;
		}
	}

	img {
		display: block;
		max-width: 100%;
		object-fit: cover;
	}

	.wrapper {
		display: grid;
		place-content: center;
		height: 100%;
	}

	.marquee {
		overflow: hidden;
		position: relative;
		mask-image: linear-gradient(
			var(--mask-direction, to right),
			hsl(0 0% 0% / 0),
			hsl(0 0% 0% / 1) 10%,
			hsl(0 0% 0% / 1) 90%,
			hsl(0 0% 0% / 0)
		);
	}

	.marquee-container {
		display: flex;
		width: 100%;
	}

	.marquee-track {
		display: flex;
	}

	@supports (-webkit-touch-callout: none) {
		.marquee-container {
			transform: translate3d(0, 0, 0) scale(1);
			perspective: 1px;
		}
	}

	.marquee-item {
		display: flex;
		align-items: center;
		justify-content: center;

		flex-shrink: 0;

		width: 160px;
		margin-inline-end: 3rem;

		img {
			height: 160px;
			width: 100%;
			object-fit: contain;
			backface-visibility: hidden;
			filter: brightness(100%);
		}
	}
</style>
