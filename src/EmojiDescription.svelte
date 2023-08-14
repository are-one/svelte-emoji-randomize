<script>
    import {onMount, onDestroy, beforeUpdate, afterUpdate} from "svelte";

    let description = '';

    // 
    $: characters = description.length;
    $: words = characters > 0 ? description.split(' ').length : 0;

    onMount(function() {
        console.log('onMount');
    });

    onDestroy(function() {
        console.log('onDestroy');
    });

    beforeUpdate(function() {
        console.log('beforeUpdate');
    });

    afterUpdate(function () {
        console.log('afterUpdate');
    });
</script>

<style></style>


<div>
    <p>{description}</p>
    <textarea bind:value={description}></textarea>
    <p>Characters count: {characters}</p>
    <p>Words count: {words}</p>
</div>
