<script>
	// import the Modal component
	import Modal from './Modal.svelte';

	let people = [
		{ name: 'Bonnie Gachiengu', beltColor: 'orange', age: 30, id: 1 },
		{ name: 'Enzo Ferrari', beltColor: 'red', age: 45, id: 2 },
		{ name: 'Robert Einstein', beltColor: 'black', age: 40, id: 3 },
		{ name: 'Neil deGrasse Tyson', beltColor: 'green', age: 60, id: 4 }
	];

	const handleClick = (id) => {
		// remove the last person from the array people
		people = people.filter(person => person.id !== id);
	}

	let num = 20;

</script>

<!--Conditionals-->
<!-- {#if num > 4}
	<p>Number is greater than 4</p>
{:else if num < 4}
	<p>Number is less than 4</p>
{:else}
	<p>Number is 4</p>
{/if} -->

<!--Component - Modal-->
<Modal />

<!--Component - Main content-->
<main>
	{#each people as person (person.id)}
		<div class="person">
			<h2>{person.name}</h2>
			<!--Another conditional-->
			{#if person.beltColor === 'black'}
				<p><strong>MASTER NINJA</strong></p>
			{/if}
			<p>{person.age} years old</p>
			<p style="color: {person.beltColor};">{person.beltColor} belt</p>
			<button class="btn" on:click={() => handleClick(person.id)}>delete</button>
		</div>
		{:else}
		<p>No people to display...</p>
	{/each}
</main>

<style>
	.person {
		padding: 0.2em;
		margin: 0.2em 0;
	}


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>