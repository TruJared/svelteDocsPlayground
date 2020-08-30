<!-- YOU ARE HERE: https://svelte.dev/tutorial/tweened -->

<script>
    import NameChanger from './FormInput.svelte';
    import FormInput from './FormInput.svelte';
    import Destructuring from './Destructuring.svelte';
    import Each from './Each.svelte';
    import Yodify from './Yodify.svelte';
    import EventDispatcher from './EventDispatcher.svelte';
    import Bindings from './Bindings.svelte';
    import LifeCycleMethods from './LifeCycleMethods.svelte';
    import FormOutput from './FormOutput.svelte';
    	import { time } from './stores.js';


    const htmlString = '&lt;div&gt';

    const warhammer = {
        faction: 'Lizardmen',
        leaderName: 'Kroc-gar',
        winning: true,
    };

    let urls = [
        {
            pageName: 'Each Blocks',
            pageUrl: 'https://svelte.dev/tutorial/each-blocks',
        },
        {
            pageName: 'Keyed Each Blocks',
            pageUrl: 'https://svelte.dev/tutorial/keyed-each-blocks',
        },
    ];

	const formatter = new Intl.DateTimeFormat('en', {
		hour12: true,
		hour: 'numeric',
		minute: '2-digit',
		second: '2-digit'
	});


    function handleMessage(event) {
        alert(event.detail.text);
    }
</script>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }
    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 3em;
        font-weight: 100;
    }
</style>

<main>
    <h1>Welcome To: Dumb Svelte App!!!</h1>
    <p>
        Random HTML string just because ➡
        {@html htmlString}
    </p>
    <h2>Reactivity Statement</h2>
    <FormInput />
    <h2>Form Output</h2>
    <h3>
        Everything here is output from above (it's passed here using
        <a href="https://svelte.dev/tutorial/writable-stores" target="_blank">
            <code>stores</code>
        </a>
        )
    </h3>
    <FormOutput />
    <h2>This is a an example of using destructing in a component</h2>
    <Destructuring {...warhammer} />
    <h2>Svelte has some cool way to work with Each Blocks</h2>
    {#each urls as url}
        <Each {...url} />
    {/each}
    <h2>Yodify (uses built in Await block)</h2>
    <Yodify />
    <h2>Event Dispatcher (handy, but not many use cases)</h2>
    <EventDispatcher on:message={handleMessage} />
    <h2>Are checkboxes the greatest HTML element of all time??</h2>
    <Bindings />
    <h2>Life Cycle Methods</h2>
    <LifeCycleMethods />
    <h2>Readable Stores</h2>
    <h3>Stores can be readable too. For example no need to have "time" be writable:</h3>
    <h4>The time is {formatter.format($time)}</h4>
    <p>*NOTE: You can even have <a href="https://svelte.dev/tutorial/derived-stores" target="_blank"><code>derived values</code></a> in Svelte. Or be a real baller and create <a href="https://svelte.dev/tutorial/custom-stores" target="_blank"><code>custom stores</code></a>.</p>

</main>
