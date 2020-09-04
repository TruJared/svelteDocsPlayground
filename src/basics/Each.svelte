<script>
    export let pageName;
    export let pageUrl;
</script>

<style>
    span {
        display: inline-block;
        padding: 0.2em 0.5em;
        margin: 0 0.2em 0.2em 0;
        text-align: center;
    }
</style>

<p>
<a href={pageUrl}>{pageName}</a>
</p>
