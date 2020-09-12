<!-- https://svelte.dev/tutorial/slots -->
<script>
    let big = false;
</script>

<style>
    .big {
        font-size: 4em;
    }

    :global(body.dark-mode) {
        background: goldenrod;
    }
</style>

<label> <input type="checkbox" bind:checked={big} /> big </label>

<div class:big>some {big ? 'big' : 'small'} text</div>
<div>
    <button
        class="button"
        on:click={() => window.document.body.classList.toggle('dark-mode')}>Toggle
        Mustard Mode</button>
</div>
