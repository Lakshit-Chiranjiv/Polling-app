<script>
    export let poll;
    let votes = poll.votes;
    let totalVotes = votes.reduce((a, b) => a + b, 0);
    let percentages = votes.map(vote => `${vote / totalVotes * 100}%`);
</script>

<main class="p-8 border-2 rounded">
    <h2 class="text-2xl font-semibold mb-6">{poll.question}</h2>
    <p class="text-slate-600 mb-4">
        {poll.description}
    </p>
    <div class="flex flex-col gap-1">
        {#each poll.options as option, i}
            <button class="bg-orange-200 py-2 rounded border-l-emerald-400 border-l-4" style={`width: ${percentages[i]};`}>{option}</button>
            <br>
        {/each}
    </div>
    <p class="text-right">Total votes : {totalVotes}</p>
</main>

<style>
    
</style>