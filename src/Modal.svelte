<script>
    export let message = "default message";
    let showModal = true;
    export let dontDelete = true;
</script>

{#if showModal}
    <div class="backdrop" class:delete={dontDelete}>
        <div class="modal">
            <h2>Are you sure?</h2>
            <p>{message}</p>
            <button class="btn" on:click={() => dontDelete = false}>Yes, delete</button>
            <button class="btn btn--alt" on:click={() => showModal = false}>No, cancel</button>
        </div>
    </div>
{/if}

<style>
    .backdrop {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        background: rgba(0, 0, 0, 0.75);
        z-index: 10;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .modal {
        width: 90%;
        max-width: 40rem;
        background: white;
        border-radius: 10px;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
        padding: 1rem;
        text-align: center;
    }

    .btn {
        font: inherit;
        cursor: pointer;
        border: 1px solid #ccc;
        padding: 0.25rem 1rem;
        background: #ff2050;
        color: white;
        border-radius: 6px;
    }

    .btn--alt {
        background: #f1f1f1;
        color: #333;
        border: 1px solid #ccc;
    }

    .delete .modal {
        background: rgb(254, 206, 228);
        color: white;
    }
    
</style>