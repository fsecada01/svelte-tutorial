<script>
	import Form from './Form.svelte';
	import Fetch from './Fetch.svelte';

	let searchTerm;

	function handleSubmit() {
		const { value } = this.elements.search;
		searchTerm = value;
	}
</script>
<style>
	.SvelteContainer {
		border: 1px ridge green;
		box-shadow: 1px 3px 4px steelblue;
		font-size: 1.2rem;
		margin-bottom: 3rem;
		margin-left: auto;
		margin-right: auto;
		max-width: 1300px;
		padding: 1rem;
		text-align: center;
	}

	ul {
		text-align: justify;
	}

	form {
		text-align: justify;
	}

	input#search {
		width: 60rem;
	}
	
</style>
<div class='SvelteContainer'>
	<Form {handleSubmit} />
	<Fetch {searchTerm} let:data>
		<h1>A List of Links</h1>
		<ul>
			{#each data as link}
			<li>
				<a href={link.url} target='_blank'>{link.title}</a>
			</li>
			{/each}
		</ul>
	</Fetch>
</div>
<!-- <Fetch /> -->