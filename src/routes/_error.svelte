<script>
	export let status;
	export let error;

	const dev = process.env.NODE_ENV === 'development';
</script>

<style>

</style>

<svelte:head>
	<title>404</title>
</svelte:head>

<h1>404</h1>

{#if dev && error.stack}
	<pre>{status}</pre>
	<pre>{error.message}</pre>
	<pre>{error.stack}</pre>
{/if}
