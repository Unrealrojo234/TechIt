<script>
	// Add any reactive declarations or component logic here if needed

	let api = import.meta.env.VITE_RESEND_EMAIL_URL;

	let name = $state('');
	let email = $state('');
	let message = $state('');

	const sendEmail = (e) => {
		e.preventDefault();
		console.log('Sending email');

		fetch(`${api}/send/${email}/${message}/${name}`)
			.then((res) => res.json())
			.then((data) => {
				console.log(data);
				alert('Email sent successfully');
			})
			.catch((err) => {
				console.error(err);
			});
	};
</script>

<section class="">
	<br /><br />
	<div class="row align-items-center g-4">
		<!-- Form Area -->
		<div class="col-lg-8">
			<form onsubmit={sendEmail}>
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
								bind:value={name}
								required
								style="background-color: #0c0c0c;color:aliceblue;"
								class="form-control bg-opacity-25"
							/>
						</div>
						<div class="col-sm-6">
							<input
								bind:value={email}
								required
								type="email"
								style="background-color: #0c0c0c;color:aliceblue;"
								placeholder="Email address"
								class="form-control"
							/>
						</div>
					</div>

					<div class="mt-3">
						<textarea
							bind:value={message}
							required
							placeholder="Write message"
							style="background-color: #0c0c0c;min-height: 200px;color:aliceblue;"
							class="form-control"
						></textarea>
					</div>

					<button type="submit" class="btn w-100 mt-3 text-white">
						Send <i class="fa-sharp fa-solid fa-paper-plane fa-2xs"></i></button
					>
				</div>
			</form>
			<br /><br />
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
		background-color: none;
		border-color: teal;
		box-shadow: none;
		color: aliceblue;
	}
	p {
		font-size: larger;
	}
	button {
		border: 1px solid teal;
	}
	input,
	textarea {
		border: 1px solid teal;
	}
</style>
