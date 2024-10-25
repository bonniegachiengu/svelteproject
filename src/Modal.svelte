<script>
    // Some Event modifiers;
    // once - the event listener will be removed after the first time it runs (useful for things like alerts i.e. removes handler)
    // preventDefault - prevents the default behavior of the event (e.g. form submission or link navigation) for intance run e.preventDefault() in the handler
    // self - only trigger the handler if the event was dispatched on the element itself, not from a descendant
    // passive - indicates that the handler will never call preventDefault() on the event
    // capture - the event will be dispatched to the handler before it reaches the target element
    // stopPropagation - stops the event from propagating further (e.g. from a child to a parent element)
    

    export let message = "default message";
    export let showModal = false;
    export let dontDelete = false;
</script>

{#if showModal}
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="backdrop" class:delete={dontDelete} on:click|self>
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