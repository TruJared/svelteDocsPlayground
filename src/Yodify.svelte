<!-- must be built pretty specifically to work correctly https://svelte.dev/tutorial/await-blocks -->

<script>
    const yodaApi = 'https://yoda-api.appspot.com/api/v1/yodish?text=';
    let yodified = yodifyIt(null);

    async function yodifyIt(event) {
        if (event) {
            const res = await fetch(
                `${yodaApi}${event.target.previousElementSibling.value}`
            );
            const yodaRes = await res.json();
            console.log(yodaRes);
            return yodaRes.yodish;
        } return 'Output appears here, it will.'
    }

    function handleClick() {
        yodified = yodifyIt(event);
    }
</script>

<style>
    div {
        border: 1px solid #bada55;
        padding: 0.5em 0;
        background: rgba(187, 218, 85, 0.363);
        border-radius: 15px;
    }
</style>

<div>
    <input id="yodifyInput" type="text" placeholder="Enter text to yodify" />
    <!-- svelte-ignore missing-declaration -->
    <button on:click={handleClick}>Yodify</button>
    {#await yodified}
        <p>Calling Yoda</p>
    {:then data}
        <h3>{data}</h3>
    {/await}
</div>
