<script>
	import { onMount, onDestroy } from 'svelte';
	import EmblaCarousel from 'embla-carousel';

	let embla;
	let viewport;
	let autoScroll;

	const startAutoScroll = () => {
		autoScroll = setInterval(() => {
			if (embla) embla.scrollNext(); // Move to the next slide
		}, 3000); // Adjust the delay as needed
	};

	const stopAutoScroll = () => {
		clearInterval(autoScroll);
	};

	onMount(() => {
		embla = EmblaCarousel(viewport, {
			loop: true,
			speed: 5
		});
		startAutoScroll();

		// Stop scrolling on hover
		viewport.addEventListener('mouseenter', stopAutoScroll);
		viewport.addEventListener('mouseleave', startAutoScroll);
	});

	onDestroy(() => {
		stopAutoScroll();
	});
</script>

<div class="embla">
	<div class="embla__viewport" bind:this={viewport}>
		<div class="embla__container">
			<div class="embla__slide">Slide 1</div>
			<div class="embla__slide">Slide 2</div>
			<div class="embla__slide">Slide 3</div>
		</div>
	</div>
</div>

<style>
	.embla {
		overflow: hidden;
	}
	.embla__viewport {
		overflow: hidden;
		max-width: 48rem;
		display: block;
		margin: auto;
	}
	.embla__container {
		display: flex;
	}
	.embla__slide {
		min-width: 100%;
		padding: 1em;
		min-height: 22rem;
		border: 1px solid teal;
		text-align: center;
	}
</style>
