<script>
    import NameChanger from './NameChanger.svelte';
    import ReactivityStatement from './ReactivityStatement.svelte';
    import Destructuring from './Destructuring.svelte';
    import Each from './Each.svelte';
    import Yodify from './Yodify.svelte';

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
    <NameChanger appTitle="User Form" />
    <h2>Reactivity Statemet</h2>
    <ReactivityStatement />
    <h2>This is a an example of using destructing in a component</h2>
    <Destructuring {...warhammer} />
    <h2>Svelte has some cool way to work with Each Blocks</h2>
    {#each urls as url}
        <Each {...url} />
    {/each}
    <h2>Yodify (uses built in Awiat block)</h2>
    <Yodify />
</main>

<!-- you are here !! https://svelte.dev/tutorial/keyed-each-blocks -->
