<script>
	import { onMount } from 'svelte';

	let skills = [];

	onMount(async () => {
		const skillFiles = [
			{ name: 'Android', logo: '/android.svg' },
			{ name: 'html', logo: '/html5.svg' },
			{ name: 'Bootstrap', logo: '/bootstrap5.svg' },
			{ name: 'css', logo: '/css.svg' },
			{ name: 'chromium', logo: '/chromium.svg' },
			{ name: 'brave', logo: '/brave.svg' },
			{ name: 'firefox', logo: '/firefox.svg' },
			{ name: 'React', logo: '/reactjs.svg' },
			{ name: 'jquery', logo: '/jquery.svg' },
			{ name: 'svelte', logo: '/sveltejs.svg' },
			{ name: 'javascript', logo: '/javascript.svg' },
			{ name: 'kotlin', logo: '/kotlin.svg' },
			{ name: 'nodejs', logo: '/nodejs.svg' },
			{ name: 'express', logo: '/expressjs-light.svg' },
			{ name: 'python', logo: '/python.svg' },
			{ name: 'supabase', logo: '/supabase.svg' },
			{ name: 'sublime', logo: '/sublime.svg' },
			{ name: 'git', logo: '/git.svg' },
			{ name: 'github', logo: '/github-light.svg' },
			{ name: 'linux', logo: '/linux.svg' },
			{ name: 'mongodb', logo: '/mongodb.svg' },
			{ name: 'flask', logo: '/flask-light.svg' },
			{ name: 'java', logo: '/java.svg' },
			{ name: 'c', logo: '/c.svg' },
			{ name: 'docker', logo: '/docker.svg' },
			{ name: 'prettier', logo: '/prettier.svg' }

			// Add more skills here
		];
		skills = skillFiles;
	});
</script>

<main>
	<br /><br />
	<h2>Our Expertise</h2>
	<p>
		We are a team of tech enthusiasts with a diverse range of skills and expertise. Our members come
		from different backgrounds and have a wide variety of interests, which allows us to tackle a
		broad spectrum of projects and challenges. Here are some of the key areas we specialize in:
	</p>
	<ul>
		<li>Web Development</li>
		<li>Mobile App Development</li>
		<li>Machine Learning</li>
		<li>Artificial Intelligence</li>
		<li>Cloud Computing</li>
		<li>Internet of Things (IoT)</li>
		<li>Blockchain Technology</li>
		<li>UI/UX Design</li>
		<li>Software Engineering</li>
		<li>Cyber security</li>
	</ul>
	<div>
		<h2>Tools</h2>
		{#await skills}
			<p>loading...</p>
		{:then skills}
			<!-- Multiple items -->
			<div class="scroll-container gradient-edges pause-on-hover">
				<div class="scroll-text scroll-multiple">
					<!-- svelte-ignore a11y_distracting_elements -->
					<marquee behavior="scroll" direction="left">
						{#each skills as skill}
							<img src={skill.logo} alt={skill.name} />
						{/each}
					</marquee>
				</div>
			</div>
		{:catch error}
			<p>{error.message}</p>
		{/await}
	</div>
	<p>
		Whether you need a website, a mobile app, or a custom software solution, we have the skills and
		expertise to bring your ideas to life. Our team is dedicated to delivering high-quality tech
		solutions that meet your needs and exceed your expectations. Let us help you turn your vision
		into reality!
	</p>
</main>

<style>
	p {
		font-size: larger;
	}
	img {
		width: 4rem;
		height: auto;
		margin: 10px;
	}

	/* Basic scrolling container */
	.scroll-container {
		overflow: hidden;
		position: relative;
		width: 100%;
	}

	@keyframes scrollText {
		from {
			transform: translateX(100%);
		}
		to {
			transform: translateX(-100%);
		}
	}

	/* Smooth pause on hover */
	.pause-on-hover .scroll-text {
		animation-play-state: running;
	}

	.pause-on-hover:hover .scroll-text {
		animation-play-state: paused;
	}

	/* Multiple items */
	.scroll-multiple {
		display: flex;
		gap: 20px;
	}

	/* Gradient fade edges */
	.gradient-edges {
		-webkit-mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
		mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
	}
</style>
