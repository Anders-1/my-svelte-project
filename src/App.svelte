<svelte:head>
	<link rel="stylesheet" href="https://unpkg.com/chota@latest">
</svelte:head>

<script>

	import { onMount } from 'svelte';

	// Brand variables (remove export later)
	export let name;
	let icon_light = './images/icon-light.svg';
	let icon_dark = './images/icon-dark.svg';

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
			<img class:is-hidden="{isdark}" src={icon_light} alt="Light spy icon">
			<img class:is-hidden="{!isdark}" src={icon_dark} alt="Dark spy icon">
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
