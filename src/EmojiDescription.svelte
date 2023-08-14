<script>
    let description = '';

    // 
    $: characters = description.length;
    $: words = characters > 0 ? description.split(' ').length : 0;
</script>

<style></style>


<div>
    <p>{description}</p>
    <textarea bind:value={description}></textarea>
    <p>Characters count: {characters}</p>
    <p>Words count: {words}</p>
</div>
