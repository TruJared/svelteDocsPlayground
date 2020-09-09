<!-- you are here https://svelte.dev/tutorial/in-and-out -->
<script>
    import Transitions from './Transitions.svelte';
    import Fade from './Fade.svelte';
    import Typewriter from './Typewriter.svelte'
</script>

<style>
    ul {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;

    }
    li {
        list-style: none;
        padding: 0 2px;
    }

</style>
<h2>Transitions</h2>
<h3>Progress Bar</h3>
<Transitions />

<h3>Spring</h3>
<p>Check it out in the <a href="https://svelte.dev/tutorial/spring" target="_blank">docs</a></p>

<h3>Fade & Fly</h3>
<h4>NOTE: Looks unusual because the previous transition is not technically "resetting" before the new one is added.</h4>
<Fade />

<h3>There are many different ways to create transitions:</h3>
<ul>
<li><a href="https://svelte.dev/tutorial/custom-css-transitions" target="_blank">| Css Transitions |</a></li>
<li><a href="https://svelte.dev/tutorial/custom-js-transitions" target="_blank">| JS Transitions (see typewritter below) |</a></li>
<li><a href="https://svelte.dev/tutorial/transition-events" target="_blank">| Transitions have events |</a></li>
<li><a href="https://svelte.dev/tutorial/local-transitions" target="_blank">| Local transitions (my guess is not many use cases, but not sure) |</a></li>
<li><a href="https://svelte.dev/tutorial/deferred-transitions" target="_blank">| Deferred transitions and the animate directive is a game-changer</a> (See Example App ⬆) |</li>
</ul>
<h4>Typewriter</h4>
<Typewriter />
