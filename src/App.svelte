<script>
	let name = 'Yoshi';
	let beltColor = 'black';

	const handleClick = () => {
		beltColor = beltColor === 'black' ? 'white' : 'black';
	};
</script>

<!--Component - Main content-->
<main>
	<h1>Hello {name}!</h1>
	<p>{beltColor} belt</p>
	<button on:click={handleClick}>Change belt color</button>
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