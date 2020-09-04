<script>
    import Basics from './basics/Basics.svelte';
    import Animations from './animations/Animations.svelte';

    let activeButton = 'animations';
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

    .active {
        color: white;
        background: #ff3e00;
    }
</style>

  <main>
    <h1>Welcome To: Dumb Svelte App!!!</h1>
    <div class="pageSelector--loader">
        <button
            class="button"
            class:active={activeButton === 'basics'}
            on:click={() => (activeButton = 'basics')}>Basics</button>
        <button
            class="button"
            class:active={activeButton === 'animations'}
            on:click={() => (activeButton = 'animations')}>Animations</button>
    </div>
    {#if activeButton === 'basics'}
        <Basics />
    {:else}
        <Animations />
    {/if}
</main>
