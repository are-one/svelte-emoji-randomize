<script>
	import EmojiDisplay from "./EmojiDisplay.svelte";
	import EmojiDescription from "./EmojiDescription.svelte";
	import Button from "./Button.svelte";

	let currentEmoji = '😁';
	const emojis = ['🤣', '😊', '😍','🚀'];

	function randomizeEmoji() {
		return emojis[Math.floor(Math.random() * emojis.length)];
	}

	function handleRandomButton() {
		currentEmoji = randomizeEmoji();
	}
</script>

<style>
 div {
	margin: 2em;
 }
</style>

<svelte:head>
	<link rel="stylesheet" href="/terminal.min.css" />
</svelte:head>

<div class="container">
	<h1>Randomize Emoji</h1>
	<EmojiDisplay {currentEmoji} />
	<EmojiDescription />
	<Button on:click={handleRandomButton} title={'🔁 Randomize'}/>
</div>