<script>
    export let currentEmoji;
	setTimeout(function(){
		currentEmoji = '😥';
	},1000);

    let current = 'button1';
</script>

<style>
    /* 
    Menerapkan style ke semua Component svelte dengan menggunakan :global()
    :global(div) {
        font-size: 3em;
        margin-bottom: 0.5em;
    } 
    */

    div {
        font-size: 3em;
        margin-bottom: 0.5em;
    }

</style>

<div>{currentEmoji}</div>
<button
    class="btn"
    class:btn-primary={current == 'button1'}
    on:click={() => current = 'button1'}
    >Button 1</button>

<button
    class="btn"
    class:btn-primary={current == 'button2'}
    on:click={() => current = 'button2'}
    >Button 2</button>
    
<button
    class="btn"
    class:btn-primary={current == 'button3'}
    on:click={() => current = 'button3'}
    >Button 3</button>

<p>{current.charAt(0).toUpperCase() + current.slice(1).toLowerCase()} di klik!</p>