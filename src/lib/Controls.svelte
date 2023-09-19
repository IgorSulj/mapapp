<script lang="ts">
    import { routeNames } from "./route_descriptions";

    export let route: number | undefined = undefined
    export let isOnRoutePage = false
</script>

<div id="top-bar">
    <button on:click={() => isOnRoutePage = false}>
        <div class="top-bar__elem" class:active={!isOnRoutePage}>
            Маршруты
        </div>
    </button>
    <button on:click={() => route != undefined && (isOnRoutePage = true)}>
        <div class="top-bar__elem" 
            class:disabled={route === undefined}
            class:active={isOnRoutePage}
            >
            {#if route !== undefined}
                {routeNames[route]}
            {:else}
                Не выбрано
            {/if}
        </div>
    </button>
</div>

<style>
    #top-bar {
        display: flex;
        justify-content: center;
        margin-bottom: 20px;
    }

    .top-bar__elem {
        --button-color: black;
        padding: 0.625rem;
        color: var(--button-color);
        border-bottom: 1px solid var(--button-color);
        min-width: 6.25rem;
        text-align: center;
    }

    .active {
        --button-color: #E3CD00;
    }

    .disabled {
        --button-color: #A9A9A9;
    }

    button {
        background-color: transparent;
        border: none;
        margin: 0;
        padding: 0;
        cursor: pointer;
    }
</style>
