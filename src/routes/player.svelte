<script>
    export let player;
</script>

{#if player === 'x'}
     <img src="./coffee-time.png" alt="player x" />
{:else if player === 'o'}
     <img src="./guitar.png" alt="player o" />
{/if}

<style>
     img{
        width: 64px;
        height: 64px;
     }
</style>