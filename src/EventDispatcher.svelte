<!-- typically dispatchers will not be needed but they have a good use case for certain situations https://github.com/sveltejs/svelte/issues/2323#issuecomment-569954265 -->
<!-- In some cases event forwarding can resolve this issue more efficiently https://svelte.dev/tutorial/event-forwarding and https://svelte.dev/tutorial/dom-event-forwarding-->
<script>
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	function sayHello() {
		dispatch('message', {
			text: 'Hello!'
		});
	}
</script>

<button on:click={sayHello}>
	Click to say hello
</button>
