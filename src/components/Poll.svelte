<script>
    export let poll;
</script>

<main class="m-6 p-8 border-2 rounded">
    <h2 class="text-2xl font-semibold mb-6">{poll.question}</h2>
    <p class="text-slate-600 mb-4">
        {poll.description}
    </p>
    <div class="flex flex-col gap-4">
        {#each poll.options as option}
            <button class="bg-orange-200 text-white py-2 rounded">{option}</button>
        {/each}
    </div>
</main>

<style>
    
</style>