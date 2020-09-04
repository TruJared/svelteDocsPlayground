<script>
    export let faction;
    export let leaderName;
    export let winning = false;
</script>

<p>{leaderName} of the {faction} is {winning ? 'winning' : 'losing'} </p>
