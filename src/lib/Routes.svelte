<script lang="ts">
    import { createEventDispatcher } from "svelte";
    import Route from "./Route.svelte";
    import { routeNames } from "./route_descriptions";

    const dispatch = createEventDispatcher<{
        routeClicked: number
    }>()
</script>
<div id="wrapper">
    {#each routeNames as routeName, index }
        <Route text={routeName}
         {index}
         on:click={() => dispatch("routeClicked", index)} />
    {/each}
</div>

<style>
    #wrapper {
        display: flex;
        flex-direction: column;
        gap: 0.625rem;
        margin-bottom: 2rem;
    }
</style>
