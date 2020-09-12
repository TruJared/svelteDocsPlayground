<!-- you are here and this needs read https://svelte.dev/tutorial/context-api -->

<script>
    import Classes from "./Classes.svelte";
    import CompComp from "./ComponentComposition.svelte"
    import SlotProps from "./SlotProps.svelte"
</script>

<style>
	div {
		padding: 1em;
		margin: 0 0 1em 0;
		background-color: #eee;
	}

	.active {
		background-color: #ff3e00;
		color: white;
	}</style>

<h2>Advanced</h2>
<h3>Not really "advanced" more like less basic basics </h3>

<h2>Actions</h2>
<p><a href="https://svelte.dev/tutorial/actions" target="_blank">Actions</a> are essentially element-level lifecycle functions.</p>
<p>It can be a little confusing to understand, check out these articles on <a href="https://medium.com/better-programming/practical-svelte-the-use-directive-60635671335f" target="_blank">medium</a> and <a href="https://codechips.me/the-use-for-use-in-svelte/" target="_blank">codechips</a></p><p>Be sure to also read <a href="https://svelte.dev/tutorial/adding-parameters-to-actions" target="_blank">adding parameters</a> to actions.</p>
<h2>The Class Directive (A.K.A. my favorite feature)</h2>
<h3>Pretty simple really, but gets used frequently and is really clean to write.</h3>
<Classes />

<h2>Component Composition</h2>
<h3>Components can have children. This is done using the <code>&#60;slot&#62;</code> element.</h3>
<CompComp>This was passed as a child of the component<p slot="used">This is a named slot</p></CompComp>
<h2>And if you're a real maniac, <code>slots</code> can even have <code>props</code> 😱</h2>
<SlotProps let:hovering={active}>
	<div class:active>
		{#if active}
			<p>I am being hovered upon.</p>
		{:else}
			<p>Hover over me!</p>
		{/if}
	</div>
</SlotProps>
<h2>Context API</h2>
<p>This is an actual "advanced" topic. Read about it in the <a href="https://svelte.dev/tutorial/context-api" target="_blank">Svelte Docs</a>. There is also a very detailed answer at <a href="https://stackoverflow.com/questions/61387774/svelte-usage-of-context-api-setcontext-getcontext-over-regular-props-passing#answer-61391664" target="_blank">Stack Overflow</a>.</p>
<p>A good way to look at context vs. stores is that context is NOT reactive while stores is.</p>
<h2>Special Elements in Svelte</h2>
<li><a href="https://svelte.dev/tutorial/svelte-self" target="_blank">svelte:self</a></li>
<li><a href="https://svelte.dev/tutorial/svelte-component" target="_blank">svelte:component</a></li>
<li><a href="https://svelte.dev/tutorial/svelte-window" target="_blank">svelte:window</a></li>
<li><a href="https://svelte.dev/tutorial/svelte-window-bindings" target="_blank">svelte:window -- bindings</a></li>
<li><a href="https://svelte.dev/tutorial/svelte-body" target="_blank">svelte:body</a></li>
<li><a href="https://svelte.dev/tutorial/svelte-head" target="_blank">svelte:head</a></li>
<li><a href="https://svelte.dev/tutorial/svelte-options" target="_blank">svelte:options</a></li>
