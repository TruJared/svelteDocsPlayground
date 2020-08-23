<script>
    import NameChanger from './NameChanger.svelte';
    import ReactivityStatement from './ReactivityStatement.svelte'
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
</style>

<main>
    <NameChanger appTitle="User Form" />
    <ReactivityStatement />
</main>

<!-- you are here !! https://svelte.dev/tutorial/keyed-each-blocks -->
