<script>
	import EmojiDisplay from "./EmojiDisplay.svelte";
	import EmojiDescription from "./EmojiDescription.svelte";
	import Button from "./Button.svelte";

	let isLoaded = false;
	let currentEmoji = '😁';
	const emojis = ['🤣', '😊', '😍','🚀'];
	let m = {x: 0, y: 0};

	function randomizeEmoji() {
		return emojis[Math.floor(Math.random() * emojis.length)];
	}

	function handleRandomButton() {
		currentEmoji = randomizeEmoji();
	}

	function handleMousemove(event) {
		m.x = event.clientX;
		m.y = event.clientY;
	}

	setTimeout(function() {
		isLoaded = true;
	}, 2500);
</script>

<style>
 div {
	margin: 2em;
 }
</style>

<svelte:head>
	<link rel="stylesheet" href="/terminal.min.css" />
</svelte:head>

<div class="container" on:mousemove={handleMousemove}>
	<p>The mouse position: {m.x} x {m.y}</p>
	<h1>Randomize Emoji</h1>
	{#if isLoaded === true}
		<EmojiDisplay {currentEmoji} />
		<EmojiDescription />
		<Button on:click={handleRandomButton} title={'🔁 Randomize'}/>
	{:else}
		<h2>Loading...</h2>
	{/if}
</div>