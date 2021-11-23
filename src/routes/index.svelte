<script context="module">
	export const prerender = true;
</script>

<script>
	import Button, { Label } from '@smui/button';
	import Counter from '$lib/Counter.svelte';
	let clicked = 0;
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<!-- <h1>
		<div class="welcome">
			<picture>
				<source srcset="svelte-welcome.webp" type="image/webp" />
				<img src="svelte-welcome.png" alt="Welcome" />
			</picture>
		</div>

		to your new<br />SvelteKit app
	</h1>

	<h2>
		try editing <strong>src/routes/index.svelte</strong>
	</h2>

	<Counter /> -->
	<div>
		<Button on:click={() => clicked++}>
		  <Label>Default</Label>
		</Button>
		<Button on:click={() => clicked++} disabled>
		  <Label>Disabled</Label>
		</Button>
		<Button on:click={() => clicked++} ripple={false}>
		  <Label>No Ripple</Label>
		</Button>
		<!--
		  Note: to target this class, you need to use
		  a :global() selector. See the styles below.
		-->
		<Button on:click={() => clicked++} class="myClass">
		  <Label>With a Class</Label>
		</Button>
	  </div>

	  <pre class="status">Clicked: {clicked}</pre>

</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}

	* :global(.myClass) {
	  font-style: italic;
	}
</style>

