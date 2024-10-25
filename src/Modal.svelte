<script>
    export let message = "default message";
    export let showModal = false;
    export let dontDelete = false;
</script>

{#if showModal}
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="backdrop" class:delete={dontDelete} on:click>
        <div class="modal">
            <p>{message}</p>
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

    .delete .modal {
        background: rgb(254, 206, 228);
        color: white;
    }
    
</style>