<script>
    export let currentEmoji;
	setTimeout(function(){
		currentEmoji = '😥';
	},1000);

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