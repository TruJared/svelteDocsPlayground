<!-- todo make component work better https://svelte.dev/tutorial/await-blocks -->

<script>
    const yodaApi = 'https://yoda-api.appspot.com/api/v1/yodish?text=';
    let yodified = 'Yodified text output appears here, it will.';

    async function yodifyIt(event) {
        let res = await fetch(
            `${yodaApi}${event.target.previousElementSibling.value}`
        );
        res = await res.json();
        console.log(res);
        yodified = res.yodish;
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
    <button on:click={() => yodifyIt(event)}>Yodify</button>
    <h3>{yodified}</h3>
</div>
