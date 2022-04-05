<svelte:head>
	<link rel="stylesheet" href="https://unpkg.com/chota@latest">
</svelte:head>

<script>

	import { onMount } from 'svelte';

	export let name;

	let isdark = false;


	if (window.matchMedia &&
			window.matchMedia('(prefers-color-scheme: dark)').matches) {
		document.body.classList.add('dark');
		isdark = true;
	}


	function handleClick() {
		alert("Hello " + name)
	}

</script>


<nav class="nav">
  <div class="nav-left">
    <a class="brand" href="#">{name}</a>
		<a class="brand">
			<svg class:is-hidden="{isdark}" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M17 13a4 4 0 1 1-4 4h-2a4 4 0 1 1-.535-2h3.07A3.998 3.998 0 0 1 17 13zM7 15a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm10 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4zM16 3a4 4 0 0 1 4 4v3h2v2H2v-2h2V7a4 4 0 0 1 4-4h8zm0 2H8c-1.054 0-2 .95-2 2v3h12V7c0-1.054-.95-2-2-2z"/></svg>
			<svg class:is-hidden="{!isdark}" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill="none" d="M0 0h24v24H0z"/><path d="M17 13a4 4 0 1 1-4 4h-2a4 4 0 1 1-.535-2h3.07A3.998 3.998 0 0 1 17 13zM7 15a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm10 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4zM16 3a4 4 0 0 1 4 4v3h2v2H2v-2h2V7a4 4 0 0 1 4-4h8zm0 2H8c-1.054 0-2 .95-2 2v3h12V7c0-1.054-.95-2-2-2z" fill="rgba(255,255,255,1)"/></svg>
		</a>
    <div class="tabs">
      <a>Link 1</a>
      <a class="active">Link 2</a>
    </div>
  </div>
  <div class="nav-right">
    <a class="button outline" on:click={handleClick}>Button</a>
  </div>
</nav>

<style>
	/* :root {
		--bg-color: pink !important;
	}
	:global(body.dark) {
		--bg-color: lightblue;
	} */
	:global(body.dark) {
		--bg-color: #000;
		--bg-secondary-color: #131316;
		--font-color: #f5f5f5;
		--color-grey: #ccc;
		--color-darkGrey: #777;
	}
</style>
