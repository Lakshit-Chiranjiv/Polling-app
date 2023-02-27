<script>
    // import { createEventDispatcher } from "svelte";
    import PollStore from "../stores/PollStore";
    import delIcon from '../assets/del.png'

    // const dispatch = createEventDispatcher();

    export let poll;
    $: votes = poll.votes;
    $: totalVotes = votes.reduce((a, b) => a + b, 0);
    $: percentages = votes.map(vote => `${vote / totalVotes * 100}%`);

    function optionClick(index, pollId) {
        // dispatch("vote", { index, pollId });
        PollStore.update(polls => {
            let copiedPolls = [...polls];
            let upvotedPoll = copiedPolls.find(poll => poll.id === pollId);
            upvotedPoll.votes[index]++;
            return copiedPolls;
        })
    }

</script>

<main class="p-8 border-2 rounded">
    <h2 class="text-2xl font-semibold mb-6">{poll.question}</h2>
    <p class="text-slate-600 mb-4">
        {poll.description}
    </p>
    <div class="flex flex-col gap-2">
        {#each poll.options as option, i}
            <button class="rounded border-l-emerald-400 border-l-4 relative" on:click={() => optionClick(i,poll.id)}>
                <div class="bg-orange-100 h-full absolute box-border rounded-r -z-20" style={`width: ${percentages[i]};`}></div>
                <p class="my-2">{option} - {votes[i]}</p>
            </button>
        {/each}
    </div>
    <div class="flex justify-between items-center mt-8">
        <p>Time Left : 2h</p>
        <p class="bg-green-300 p-2 px-4 rounded">Total votes : {totalVotes}</p>
        <button class="bg-red-600 p-2 rounded" on:click={() => {
            PollStore.update(polls => {
                return polls.filter(p => p.id !== poll.id)
            })
        }}>
            <img src={delIcon} alt="delete" class="w-4 h-4"/>
        </button>
    </div>
</main>

<style>
    
</style>