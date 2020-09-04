<script>
    import { fade, fly } from 'svelte/transition';
    let animations = null;
</script>

<style>
    p {
    display: inline-block;
    }
</style>


<label>
    <input type="radio" bind:group={animations} value={'fade'} /> Fade
</label>
<label>
    <input type="radio" bind:group={animations} value={'fly'} /> Fly
</label>
<label>
    <input type="radio" bind:group={animations} value={null} /> Reset
</label>
{#if animations === 'fade'}
    <p transition:fade>Fade</p>
{:else if animations === 'fly'}
    <p transition:fly={{ x: -200, duration: 3000 }}>Fly</p>
{:else}
    <p>Fade or fly</p>
{/if}
