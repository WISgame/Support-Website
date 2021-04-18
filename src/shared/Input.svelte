<script>
	//PUBLIC VARIABLES
	export let Placeholder = "...";
	export let Value       = "";
	export let Password    = false;
	export let Required    = false;
	export let Name        = "";
	export let Multiline   = false
</script>

{#if Multiline === true}
	<textarea autocomplete="off" required={Required} name={Name} cols="30" rows="10" placeholder={Required === true ? Placeholder + "*" : Placeholder}>{Value}</textarea>
{:else}
	<input autocomplete="off" required={Required} name={Name} type={Password === true ? "password" : "text"} placeholder={Required === true ? Placeholder + "*" : Placeholder} value={Value}>
{/if}


<style>
	input, textarea {
		padding: 10px 25px;
		caret-color: #FF4500;
		border-radius: 10px;
		width: 100%;
		resize: vertical;
	}

	::selection {
		background: #FF4500;
		color: #FFF;
	}
</style>