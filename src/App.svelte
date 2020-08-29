<script>
    import NameChanger from './NameChanger.svelte';
    import ReactivityStatement from './ReactivityStatement.svelte';
    import Destructuring from './Destructuring.svelte';
    import Each from './Each.svelte';
    import Yodify from './Yodify.svelte';
    import EventDispatcher from './EventDispatcher.svelte';
    import Bindings from './Bindings.svelte';
    import LifeCycleMethods from './LifeCycleMethods.svelte';

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
    <h2>Form Logic (this will make use of stores eventually)</h2>
    <NameChanger />
    <h2>Reactivity Statement</h2>
    <ReactivityStatement />
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
</main>
