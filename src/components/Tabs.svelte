<script>
    import { createEventDispatcher } from "svelte";
    export let items;
    export let active;
    const dispatch = createEventDispatcher();
</script>

<main>
    <div class="-mb-px flex justify-center gap-8">
        {#each items as item}
            <button
                class='bg-white inline-block border-l border-t border-r rounded py-2 px-4 text-blue-700 font-semibold hover:text-white hover:bg-black focus:outline-none focus:shadow-outline transition-all'
                class:text-gray-200={item === active}
                class:bg-orange-500={item === active}
                on:click={() => dispatch("change", item)}
            >
                {item}
            </button>
        {/each}
    </div>
</main>

<style>
    
</style>