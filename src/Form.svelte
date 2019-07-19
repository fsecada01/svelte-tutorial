<script>
	export let handleSubmit = function (event) {

	};

</script>

<form on:submit|preventDefault={handleSubmit}>
	<label for="search">Search:</label>
	<input for="search" id="search" required />
	<button type="submit">Search</button>
</form>