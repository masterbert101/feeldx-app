<script>
	import { onMount } from 'svelte';

	let works1 = [
		{ src: '/station.webp', alt: 'Station Image' },
		{ src: '/mrpa.webp', alt: 'MRPA Image' },
		{ src: '/college.webp', alt: 'College Image' }
	];
	let works2 = [
		{ src: '/pavilion.webp', alt: 'Pavilion Image' },
		{ src: '/sunbury.webp', alt: 'Sunbury Image' },
		{ src: '/datacentre.webp', alt: 'Data Centre Image' }
	];

	let works1Visible = false;
	let works2Visible = false;

	onMount(() => {
		const options = {
			root: null,
			threshold: 0.3
		};

		const observer = new IntersectionObserver((entries) => {
			entries.forEach((entry) => {
				if (entry.isIntersecting) {
					if (entry.target.classList.contains('works1')) {
						works1Visible = true;
					}
					if (entry.target.classList.contains('works2')) {
						works2Visible = true;
					}
				}
			});
		}, options);

		const works1El = document.querySelector('.works1');
		const works2El = document.querySelector('.works2');

		if (works1El) observer.observe(works1El);
		if (works2El) observer.observe(works2El);
	});
</script>

<section class="container">
	<header class="header">
		<h2>OUR WORK</h2>
		<p>
			We are committed to enhancing user experiences, exploring innovative audience engagement
			methods, and maximising production efficiency by adopting cutting-edge creative technologies.
		</p>
	</header>

	<div class="works-container">
		<div class="works works1 {works1Visible ? 'slide-in-right' : 'before-slide-right'}">
			{#each works1 as work}
				<a class="img-container" href="https://www.feeldx.com/our-work">
					<img src={work.src} alt={work.alt} />
					<span class="btn">View Work</span>
				</a>
			{/each}
		</div>

		<div class="works works2 {works2Visible ? 'slide-in-left' : 'before-slide-left'}">
			{#each works2 as work}
				<a class="img-container" href="https://www.feeldx.com/our-work">
					<img src={work.src} alt={work.alt} />
					<span class="btn">View Work</span>
				</a>
			{/each}
		</div>
	</div>
</section>

<style lang="scss">
	.container {
		padding: 3rem 1rem;
		@media only screen and (min-width: 640px) {
			padding: 5rem 2rem;
		}
	}

	.header {
		h2 {
			font-size: 2.75rem;
			margin: 0;
			text-transform: uppercase;

			@media only screen and (min-width: 640px) {
				font-size: 3.5rem;
			}
		}
		p {
			font-size: 0.85rem;
			@media only screen and (min-width: 640px) {
				font-size: 1rem;
				max-width: 750px;
			}
		}
	}

	.works-container {
		display: grid;
		gap: 1rem;
		padding-top: 2rem;
	}

	.works {
		display: grid;
		gap: 1rem;

		@media only screen and (min-width: 640px) {
			min-width: 900px;
			grid-template-columns: 1fr 2fr 1fr;
		}

		img {
			width: 100%;
			height: 100%;
			object-fit: cover;
			border-radius: 1rem;
		}
	}

	.img-container {
		position: relative;
		overflow: hidden;

		.btn {
			position: absolute;
			bottom: 0;
			left: 0;
			transform: translateX(-120%);
			padding: 0.85rem 2rem;
			border-radius: 999999px;
			margin: 1rem;
			text-transform: uppercase;
			font-size: 0.85rem;
			font-weight: 700;

			color: #ffff;
			background-color: #2a2f1e;
		}

		&:hover {
			.btn {
				transform: translateX(0);
				transition: transform 0.5s ease-in-out;
			}
		}
	}

	.before-slide-right {
		transform: translateX(50%);
	}

	.before-slide-left {
		transform: translateX(-50%);
	}

	.slide-in-right {
		transform: translateX(0);
		transition: transform 3s ease-in-out;
	}

	.slide-in-left {
		transform: translateX(0);
		transition: transform 3s ease-in-out;
	}
</style>
