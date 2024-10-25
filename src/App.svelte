<script>
	// import the Modal component
	import Modal from './Modal.svelte';
	import AddPersonForm from './AddPersonForm.svelte';

	let showModal = false;

	let people = [
		{ name: 'Bonnie Gachiengu', beltColor: 'orange', age: 30, id: 1, skills: ['Karate', 'Judo'] },
		{ name: 'Enzo Ferrari', beltColor: 'red', age: 45, id: 2, skills: ['Driving', 'Engineering'] },
		{ name: 'Robert Einstein', beltColor: 'black', age: 40, id: 3, skills: ['Physics', 'Mathematics'] },
	];

	const toggleModal = () => {
		showModal = !showModal;
	}

	// Delete a person when the button is clicked
	const handleDelete = (id) => {
		people = people.filter(person => person.id !== id);
	}

	const addPerson = (e) => {
		// console.log(e.detail);
		people = [e.detail, ...people];
		showModal = false;
	};

</script>

<!--Component - Modal-->
<Modal {showModal} on:click={toggleModal}>
	<AddPersonForm on:addPerson={addPerson}/>
</Modal>

<!--Component - Main content-->
<main>
	<button class="btn" on:click={toggleModal}>Toggle Modal</button>
	{#each people as person (person.id)}
		<div class="person">
			<h2>{person.name}</h2>
			<!--Another conditional-->
			{#if person.beltColor === 'black'}
				<p><strong>MASTER NINJA</strong></p>
			{/if}
			<p>{person.age} years old</p>
			<p style="color: {person.beltColor};">{person.beltColor} belt</p>
			<p>Skills: {person.skills.join(', ')}</p>
			<button class="btn" on:click={() => handleDelete(person.id)}>Delete Person</button>
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