<script>
	let firstName = 'Yoshi';
	let lastName = 'Kawasaki';
	let beltColor = 'black';

	$: fullName = `${firstName} ${lastName}`;
	$: {
		console.log(fullName);
		console.log(beltColor);
	}

</script>

<!--Component - Main content-->
<main>
	<p>{fullName} - {beltColor} belt</p>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	<input type="text" bind:value={beltColor}> <!-- Two-way binding -->
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>