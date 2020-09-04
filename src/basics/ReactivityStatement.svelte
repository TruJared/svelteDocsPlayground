<script>
    let count = 1;

   $: if (count > 100) {
        alert('AHHHHHHHHH');
    }
</script>

<p>{count}</p>
{#if count >= 10}
    <p>Don't Go Above 100!!!!!</p>
{/if}
<button on:click={() => (count = count * 2)}>Double Count</button>
