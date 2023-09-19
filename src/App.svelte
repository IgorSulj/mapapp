<script lang="ts">
    import Controls from './lib/Controls.svelte';
    import Map from './lib/Map.svelte';
    import Routes from './lib/Routes.svelte';
    import { descriptions } from './lib/route_descriptions';

    let currRoute: number | undefined = undefined
    let isOnRoutePage = false
</script>

<Map />
<Controls bind:isOnRoutePage bind:route={currRoute} />
{#if !isOnRoutePage || currRoute === undefined}
<Routes on:routeClicked={e => {
    currRoute = e.detail
    isOnRoutePage = true
}} />
{:else}
<svelte:component this={descriptions[currRoute]} />
{/if}
