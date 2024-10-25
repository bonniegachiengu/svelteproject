<script>
    let showModal = false;
</script>

{#if showModal}
    <div class="backdrop">
        <div class="modal">
            <h2>Are you sure?</h2>
            <p>Do you want to delete this person?</p>
            <button class="btn btn--alt">cancel</button>
            <button class="btn">confirm</button>
        </div>
    </div>
{/if}

<style>

    p {
		color: #4a4848;
		font-family: "Nunito Sans", sans-serif;
		font-size: 1.5;
		font-weight: 700;
	}

    .btn {
            background-color: #f43675;
            border: none;
            color: white;
            padding: 0.5em 1em;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 1em;
            margin: 0.2em 0;
            cursor: pointer;
        }

    .btn--alt {
        background-color: #f4f4f4;
        color: #f43675;
    }
    
    .btn:hover {
		background-color: #d32f5d;
	}

	.btn:active {
		background-color: #ff407f;
	}

    .btn--alt:hover {
        background-color: #a3a0a1;
        color: #ffffff;
    }

    .btn--alt:active {
        background-color: #f4f4f4;
        color: #f43675;
    }

</style>