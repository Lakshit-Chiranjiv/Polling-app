<script>
    import { createEventDispatcher } from "svelte";
    export let items;
    export let active;
    const dispatch = createEventDispatcher();
</script>

<main>
    <div class="flex justify-center gap-8 mt-12">
        {#each items as item}
            <button
                class='inline-block border-l border-t border-r rounded-t py-2 px-4 text-blue-700 font-semibold hover:text-white hover:bg-black focus:outline-none focus:shadow-outline transition-all'
                class:text-gray-200={item === active}
                class:bg-orange-500={item === active}
                on:click={() => dispatch("change", item)}
            >
                {item}
            </button>
        {/each}
    </div>
    <div class="border-b-2 border-orange-500 w-full"></div>
</main>

<style>
    
</style>