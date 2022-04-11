<script lang="ts">
	import { initClient } from '@urql/svelte';

	initClient({
		url: 'http://localhost:4000/graphql'
	});
</script>

<main>
	<slot />
</main>

<style>
	main {
		position: relative;
		max-width: 640px;
		margin: 0 auto;
		padding: 0 20px;
	}
</style>
