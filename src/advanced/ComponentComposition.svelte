<div>
    <p>This is a component illustrating a <code>default slot</code></p>
    <slot> </slot>
    <p>Below are two <code>named slots</code></p>
    <slot name="notUsed"><p>This is a fallback, as nothing was passed to the slot.</p></slot>
    <slot name="used">No need for this fallback as I'm going to use this slot</slot>
</div>
