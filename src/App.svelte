<svelte:head>
	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
	<link rel="stylesheet" href="https://unpkg.com/chota@latest">
	<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
</svelte:head>

<script>

	import { onMount } from 'svelte';

	// Brand variables (remove export later)
	let name = "world";
	let icon_light = './images/icon-light.svg';
	let icon_dark = './images/icon-dark.svg';
	let carousel_images = ['https://st3.depositphotos.com/1316534/34178/i/1600/depositphotos_341780746-stock-photo-vod-service-on-television-tv.jpg',
	 											 'https://st3.depositphotos.com/1518767/14149/i/1600/depositphotos_141491564-stock-photo-illustration-of-circuit-board.jpg',
											   'https://st2.depositphotos.com/16843704/47927/i/1600/depositphotos_479278436-stock-photo-carrara-italy-june-2021-woman.jpg']

	let isdark = false;

	// if (window.matchMedia &&
	// 		window.matchMedia('(prefers-color-scheme: dark)').matches) {
	// 	document.body.classList.add('dark');
	// 	isdark = true;
	// }


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
<h1 class="text-center">{name}</h1>
<h3 class="text-center">Have a case needing to be solved?</h3>
<h3 class="text-center">Us here at {name} have great detective skills and can solve any case you need!</h3>
<div class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active" data-bs-interval="3000" width="480" height="270">
			<img src={carousel_images[0]}>
    </div>
    <div class="carousel-item" data-bs-interval="3000">
			<img src={carousel_images[1]}>
    </div>
    <div class="carousel-item" data-bs-interval="3000">
			<img src={carousel_images[2]}>
    </div>
  </div>
</div>

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

	.carousel-item img {
		border-radius: 10px;
		display: block;
	  margin-left: auto;
	  margin-right: auto;
	  width: 50%;
		width: 500px;
	}
</style>
