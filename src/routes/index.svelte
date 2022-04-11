<script lang="ts">
	import { gql, operationStore, query } from '@urql/svelte';
	const helloQuery = gql`
		query {
			hello
		}
	`;

	const greeting = operationStore(helloQuery);
	query(greeting);
</script>

{#if $greeting.fetching}
	<p>Loading...</p>
{:else if $greeting.error}
	<p>Error: {$greeting.error.message}</p>
{:else}
	<p>{$greeting.data.hello}</p>
{/if}
