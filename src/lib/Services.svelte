<script>
	let services = [
		{
			image: '/visual.jpg',
			label: 'Visualisation',
			excerpt:
				'Content Strategy, Storytelling, 3D Visualisation, BIM 3D, 4D, 5D, Multimedia Design',
			href: 'https://www.feeldx.com/services#visualisations'
		},
		{
			image: '/project.jpg',
			label: 'Project Control',
			excerpt:
				'Construction Life Cycle Management, Project Control & Project Management, Tender Programmes, Construction Programme, Project Forensic Analysis (NOD/EOT Claims & Scheduling)',
			href: 'https://www.feeldx.com/project-control'
		}
	];

	function inViewport(node) {
		node.style.height = '225px'; // set default height
		node.style.transition = 'height 1s ease-in';

		const observer = new IntersectionObserver(
			([entry]) => {
				if (entry.isIntersecting) {
					node.style.height = '450px';
					obs.unobserve(node);
				}
			},
			{ threshold: 1 }
		);

		observer.observe(node);

		return {
			destroy() {
				observer.unobserve(node);
			}
		};
	}
</script>

<section class="container">
	<header class="header">
		<h2>Our Services</h2>
		<p>
			FeelDX specialises in crafting immersive visual experiences through cutting-edge 3D
			visualisation and creative technologies. Tailoring specialised services to diverse sectors,
			our niche teams elevate project success by aligning with unique client needs. Storytelling is
			integral, woven into our content strategy established through a meticulous discovery process,
			resulting in engaging visual content.
		</p>
	</header>

	<div class="services">
		{#each services as service, i}
			<div class="service-item">
				<img class="service-image" use:inViewport src={service.image} alt={service.label} />
				<a class="service-link" href={service.href}>
					<span>
						Read More About {service.label}
					</span>
					<svg
						width="24px"
						height="24px"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M4 12H20M20 12L14 6M20 12L14 18"
							stroke="#2a2f1e"
							stroke-width="1.5"
							stroke-linecap="round"
							stroke-linejoin="round"
						/>
					</svg>
				</a>
			</div>
		{/each}
	</div>

	<div class="capability">
		<video class="video" autoplay loop muted playsinline width="1280" height="1080">
			<source src="/herovid.mp4" type="video/mp4" />
		</video>

		<header class="capabality-header">
			<h3>Capabality Statement</h3>
			<a class="capability-link" href="https://www.feeldx.com/capability-statement">
				<span> LEARN MORE</span>
				<svg
					width="24px"
					height="24px"
					viewBox="0 0 24 24"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M4 12H20M20 12L14 6M20 12L14 18"
						stroke="#fff"
						stroke-width="1.5"
						stroke-linecap="round"
						stroke-linejoin="round"
					/>
				</svg>
			</a>
		</header>
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

	.services {
		display: flex;
		gap: 1.25rem;
		padding-top: 1rem;
		flex-direction: column;

		@media only screen and (min-width: 640px) {
			flex-direction: row;
		}
	}

	.service-item {
		width: 100%;
		height: 100%;
	}

	.service-image {
		width: 100%;
		object-fit: cover;
		transition: height 0.5s ease;
		border-radius: 1rem;
		overflow: hidden;
	}

	.service-link {
		display: flex;
		align-items: center;
		gap: 0.65rem;
		margin: 1.25rem 0 0;
		text-decoration: none;

		span {
			font-size: 1rem;
			font-weight: 600;
			color: #2a2f1e;
		}

		&:hover {
			svg {
				transform: translateX(9px);
				transition: transform 0.25s ease-in-out;
			}
		}
	}

	.capability {
		position: relative;

		padding: 3rem 0 0;
		@media only screen and (min-width: 640px) {
			padding: 5rem 0 0;
		}
	}

	.video {
		margin: 0;
		width: 100%;
		height: 100%;
		border-radius: 1rem;
	}

	.capabality-header {
		position: absolute;
		bottom: 0;
		left: 0;
		padding: 0.75rem;
		@media only screen and (min-width: 640px) {
			padding: 2rem;
		}

		h3 {
			color: #fff;
			font-size: 1.25rem;
			margin: 0;
			text-transform: uppercase;

			@media only screen and (min-width: 640px) {
				font-size: 2.5rem;
			}
		}

		.capability-link {
			display: flex;
			align-items: center;
			gap: 0.65rem;
			margin: 0;
			text-decoration: none;

			@media only screen and (min-width: 640px) {
				margin: 1.25rem 0 0;
			}

			span {
				font-size: 0.85rem;
				font-weight: 400;
				color: #fff;

				@media only screen and (min-width: 640px) {
					font-size: 1.15rem;
				}
			}

			&:hover {
				svg {
					transform: translateX(9px);
					transition: transform 0.25s ease-in-out;
				}
			}
		}
	}
</style>
