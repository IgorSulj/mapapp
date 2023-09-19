<script lang="ts">
    export let text: string
    export let index: number
</script>

<button on:click>
    <div class="wrapper">
        <div class="color"
         style="background-color: hsl({index * 40}, 100%, 50%)" />
        <p class="text">{text}</p>
    </div>
</button>

<style>
    button {
        background-color: transparent;
        border: none;
        padding: 0;
        margin: 0;
        transition: background-color 0.25s ease-out;
    }

    button:hover {
        background-color: #ccc;
    }

    .wrapper {
        display: flex;
        height: 4.5rem;
        gap: 0.625rem;
        padding-left: 1rem;
    }
    
    .color {
        height: 100%;
        width: 0.5rem;
    }

    .text {
        color: #000;
        font-family: Montserrat;
        font-size: 1.5rem;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
    }
</style>
