<script>
    let yes = false;

    let scoops = 1;
    let flavours = ['Mint choc chip'];

    function join(flavours) {
        if (flavours.length === 1) return flavours[0];
        return `${flavours.slice(0, -1).join(', ')} and ${
            flavours[flavours.length - 1]
        }`;
    }

    let questions = [
        { id: 1, text: `Where did you go to school?` },
        { id: 2, text: `What is your mother's name?` },
        {
            id: 3,
            text: `What is another personal fact that an attacker could easily find with Google?`,
        },
    ];

    let selected;

    let answer = '';

    function handleSubmit() {
        alert(
            `answered question ${selected.id} (${selected.text}) with "${answer}"`
        );
    }


    	let w;
	let h;
	let size = 42;
	let text = 'edit me';
</script>

<style>
    security-questions {
        display: block;
        width: 500px;
        max-width: 100%;
    }

    	dimentions__input { display: block; }
	dimentions__div { display: inline-block; }
	dimentsion__span { word-break: break-all; }
</style>

<label>
    <input type="checkbox" bind:checked={yes} />
    Yes!
</label>

{#if yes}
    <p>Hell yeah!</p>
{:else}
    <p>Loser</p>
{/if}

<h3>You can even bind Groups!!!! 😱</h3>

<h2>Size</h2>

<label>
    <input type="radio" bind:group={scoops} value={1} />
    One scoop
</label>

<label>
    <input type="radio" bind:group={scoops} value={2} />
    Two scoops
</label>

<label>
    <input type="radio" bind:group={scoops} value={3} />
    Three scoops
</label>

<h2>Flavours</h2>

<label>
    <input type="checkbox" bind:group={flavours} value="Cookies and cream" />
    Cookies and cream
</label>

<label>
    <input type="checkbox" bind:group={flavours} value="Mint choc chip" />
    Mint choc chip
</label>

<label>
    <input type="checkbox" bind:group={flavours} value="Raspberry ripple" />
    Raspberry ripple
</label>

{#if flavours.length === 0}
    <p>Please select at least one flavour</p>
{:else if flavours.length > scoops}
    <p>Can't order more flavours than scoops!</p>
{:else}
    <p>
        You ordered {scoops} {scoops === 1 ? 'scoop' : 'scoops'} of {join(flavours)}
    </p>
{/if}

<h2>Insecurity questions</h2>

<form on:submit|preventDefault={handleSubmit}>
    <select bind:value={selected} on:blur={() => (answer = '')}>
        {#each questions as question}
            <option value={question}>{question.text}</option>
        {/each}
    </select>

    <input class="security-questions" bind:value={answer} />

    <button disabled={!answer} type="submit">Submit</button>
</form>

<p>selected question {selected ? selected.id : '[waiting...]'}</p>


<h2>Svelte even has access to block-level element dimensions</h2>


<input class="dimensions__input" type=range bind:value={size}>
<input class="dimentions__input" bind:value={text}>

<p>size: {w}px x {h}px</p>

<div class="dimentions__div" bind:clientWidth={w} bind:clientHeight={h}>
	<span class="dimentions__span" style="font-size: {size}px">{text}</span>
</div>

<h2>You can use <code>this</code> to bind to elements and components</h2>
Example: <a href="https://svelte.dev/tutorial/bind-this">https://svelte.dev/tutorial/bind-this</a>
