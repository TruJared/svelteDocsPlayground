<script>
    import FormInput from './FormInput.svelte';
    import Destructuring from './Destructuring.svelte';
    import Each from './Each.svelte';
    import Yodify from './Yodify.svelte';
    import EventDispatcher from './EventDispatcher.svelte';
    import Bindings from './Bindings.svelte';
    import LifeCycleMethods from './LifeCycleMethods.svelte';
    import FormOutput from './FormOutput.svelte';
    import { time } from '../stores.js';

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
        second: '2-digit',
    });

    function handleMessage(event) {
        alert(event.detail.text);
    }
</script>
<h2>Basics</h2>
<p>
    Random HTML string just because ➡
    {@html htmlString}
</p>
<h3>Reactivity Statement</h3>
<FormInput />
<h3>Form Output</h3>
<h4>
    Everything here is output from above (it's passed here using <a
        href="https://svelte.dev/tutorial/writable-stores"
        target="_blank">
        <code>stores</code>
    </a> )
</h4>
<FormOutput />
<h3>This is a an example of using destructing in a component</h3>
<Destructuring {...warhammer} />
<h3>Svelte has some cool ways to work with Each Blocks</h3>
{#each urls as url}
    <Each {...url} />
{/each}
<h3>Yodify (uses built in Await block)</h3>
<Yodify />
<h3>Event Dispatcher (handy, but not many use cases)</h3>
<EventDispatcher on:message={handleMessage} />
<h3>Are checkboxes the greatest HTML element of all time??</h3>
<Bindings />
<h3>Life Cycle Methods</h3>
<LifeCycleMethods />
<h3>Readable Stores</h3>
<h4>
    Stores can be readable too. For example no need to have "time" be writable:
</h4>
<h5>The time is {formatter.format($time)}</h5>
<p>
    *NOTE: You can even have <a
        href="https://svelte.dev/tutorial/derived-stores"
        target="_blank"><code>derived values</code></a> in Svelte. Or be a real baller
    and create <a
        href="https://svelte.dev/tutorial/custom-stores"
        target="_blank"><code>custom stores</code></a>.
</p>
