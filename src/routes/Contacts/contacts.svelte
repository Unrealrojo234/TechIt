<script>
	// Add any reactive declarations or component logic here if needed
</script>

<section class="">
	<br /><br />
	<div class="row align-items-center g-4">
		<!-- Form Area -->
		<div class="col-lg-8">
			<form>
				<div class="col-lg-10 mx-auto">
					<div class="text-white">
						<h1 class="fs-2 fw-semibold lh-base">Let's connect constellations</h1>
						<p class="small mt-2 mb-4">
							Let's align our constellations! Reach out and let the magic of collaboration
							illuminate our skies.
						</p>
					</div>

					<div class="row g-3">
						<div class="col-sm-6">
							<input
								type="text"
								placeholder="Your name"
								style="background-color: #222428;"
								class="form-control bg-opacity-25 border-secondary"
							/>
						</div>
						<div class="col-sm-6">
							<input
								type="email"
								style="background-color: #222428;"
								placeholder="Email address"
								class="form-control border-secondary"
							/>
						</div>
					</div>

					<div class="mt-3">
						<textarea
							placeholder="Write message"
							style="background-color: #222428;min-height: 200px;"
							class="form-control border-secondary"
						></textarea>
					</div>

					<button
						type="submit"
						class="btn w-100 mt-3 text-white"
						style="background: linear-gradient(45deg, teal,green, lime);"
					>
						Send it to the moon
					</button>
				</div>
			</form>
		</div>

		<!-- Image
		<div class="col-lg-4">

            <img
                src="https://i.ibb.co/h7rjVJS/Image.png"
                alt="image of a person looking at the stars"
                class="img-fluid"
            />
		</div> -->
	</div>
</section>

<style>
	/* Add any additional custom styles here if needed */
	:global(.form-control:focus) {
		background-color: #222428;
		border-color: teal;
		box-shadow: none;
		color: aliceblue;
	}
	p {
		font-size: larger;
	}
</style>
