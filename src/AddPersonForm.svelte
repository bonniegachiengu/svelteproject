<script>
    import { createEventDispatcher } from "svelte";

    let dispatch = createEventDispatcher();

    let name;
    let age;
    let beltColor;
    let skills = [];

    const handleSubmit = () => {
        const person = {
            name,
            age,
            beltColor,
            skills,
            id: Math.random()
        };
        dispatch("addPerson", person);
    };

</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" id="name" bind:value={name}>
    <input type="number" placeholder="age" id="age" bind:value={age}>
    <!-- svelte-ignore a11y-label-has-associated-control -->
    <label>Skills</label>
    <input type="checkbox" bind:group={skills} value="fighting">fighting<br>
    <input type="checkbox" bind:group={skills} value="running">running<br>
    <input type="checkbox" bind:group={skills} value="sneaking">sneaking<br>
    <!-- svelte-ignore a11y-label-has-associated-control -->
    <label>Belt Color</label>
    <select bind:value={beltColor}>
        <option value="black">Black</option>
        <option value="brown">Brown</option>
        <option value="green">Green</option>
        <option value="yellow">Yellow</option>
        <option value="orange">Orange</option>
    </select>
    <button class="btn" type="submit">Add Person</button>
</form>

<style>
    form {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin: 1rem;
    }

    input {
        font: inherit;
        padding: 0.25rem;
        border-radius: 4px;
        border: 1px solid #ccc;
        margin-bottom: 0.5rem;
    }

    button {
        font: inherit;
        padding: 0.5rem 1.5rem;
        border: 1px solid #ff0055;
        background: #ff0055;
        color: white;
        border-radius: 4px;
        cursor: pointer;
    }

    button:hover,
    button:active {
        background: #ff4382;
        border-color: #ff4382;
    }
</style>