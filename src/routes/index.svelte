<script context="module" lang="ts">
	import { KQL_HelloThere } from '$lib/graphql-client/graphqlStores';
	import type { Load } from '@sveltejs/kit';
	import SendInputform from '../lib/SendInputform.svelte';

	export const load: Load = async function ({ fetch }) {
		await KQL_HelloThere.queryLoad({ fetch });
		return {};
	};
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<br />
<br />
<br />
<a href="/api/playql" target="_blank" rel="external">Graphql Playground</a>
<br />
<br />
<br />
<h2>Server says: {$KQL_HelloThere.data?.hello}</h2>
<br />
<br />
<h3>Sample form to showcase use of Felte with Zod and reporter</h3>
<p>Submitting this form will make a Graphql call and output the results to the console</p>
<SendInputform />
