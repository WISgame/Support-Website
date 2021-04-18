<script>
    //PUBLIC VARIABLES
    export let Type = "button"; // button or formsubmit
    export let Value = "Button";
</script>

{#if Type == "button"}
    <button class="btn" on:click|self >{Value}</button>
{:else if Type == "formsubmit"}
    <input class="btn" type="submit" value={Value}>
{:else}
    <p>Invalid Type Button.svelte</p>
{/if}

<style>

    .btn {
        background: #F00;
        padding: 10px 25px;
        color: #FFF;
        border: none;
        cursor: pointer;
        border-radius: 10px;
    }

    .btn:hover {
        background: linear-gradient(130deg, #F00 0%, #FF6A00 100%);
    }

    .btn:active {
        background: #FF6A00;
    }

</style>