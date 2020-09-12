<script>
    import Basics from './basics/Basics.svelte';
    import Animations from './animations/Animations.svelte';
    import NotesApp from './NotesApp.svelte';
    import Advanced from './advanced/Advanced.svelte';

    let activeButton = 'Advanced';

    const buttons = [
        { name: 'Basics', component: Basics },
        { name: 'Advanced', component: Advanced },
        { name: 'Animations', component: Animations },
        { name: 'Notes App', component: NotesApp },
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

    img {
        width: 32px;
    }

    .active {
        color: white;
        background: #ff3e00;
    }
</style>

<main>
    <h1>Welcome To: Dumb Svelte App!!!</h1>

    <h2>
        <a
            href="https://github.com/TruJared/svelteDocsPlayground"
            target="_blank"><img
                src="./GitHub-Mark-64px.png"
                alt="github logo" /> Repo</a>
    </h2>
    <div class="pageSelector--loader">
        <!-- <button
            class="button"
            class:active={activeButton === 'basics'}
            on:click={() => (activeButton = 'basics')}>Basics</button>
        <button
            class="button"
            class:active={activeButton === 'advanced'}
            on:click={() => (activeButton = 'advanced')}>Advanced</button>
        <button
            class="button"
            class:active={activeButton === 'animations'}
            on:click={() => (activeButton = 'animations')}>Animations</button>
        <button
            class="button"
            class:active={activeButton === 'notes'}
            on:click={() => (activeButton = 'notes')}>Example App</button> -->

        {#each buttons as button, index}
            <button
                class="button"
                value="index"
                class:active={activeButton === button.name}
                on:click={() => (activeButton = button.name)}>{button.name}</button>
        {/each}
    </div>
    <!-- {#if activeButton === 'Animations'}
        <Animations />
    {:else if activeButton === 'Notes App'}
        <NotesApp />
    {:else if activeButton === 'Advanced'}
        <Advanced />
    {:else}
        <Basics />
    {/if} -->

    <svelte:component
        this={buttons.find((el) => el.name === activeButton).component} />
</main>
