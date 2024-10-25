<script>
    let name;
    let age;
    let beltColor;

    const handleSubmit = () => {
        console.log(name, age, beltColor);
    };

</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" id="name" bind:value={name}>
    <input type="number" placeholder="age" id="age" bind:value={age}>
    <input type="text" placeholder="belt color" id="beltColor" bind:value={beltColor}>
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