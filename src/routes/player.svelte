<script>
     import { fly } from 'svelte/transition';

    export let player;
</script>

{#if player === 'x'}
     <img transition:fly={{ x: 100, y: 0}} src="./coffee-time.png" alt="player x" />
{:else if player === 'o'}
     <img transition:fly={{ x: -100, y: 0}} src="./guitar.png" alt="player o" />
{/if}

<style>
     img{
        width: 64px;
        height: 64px;
     }
</style>