<script>
  import Poll from "./Poll.svelte";
  import PollStore from "../stores/PollStore";
    let polls = []

    const unsub = PollStore.subscribe(value => {
        polls = value;
    })

    const handleVote = (e) => {
        const { index, pollId } = e.detail;
        let copiedPolls = [...polls];
        let upvotedPoll = copiedPolls.find(poll => poll.id === pollId);
        upvotedPoll.votes[index]++;
        polls = copiedPolls;
    }
</script>

<main class="grid grid-cols-2 gap-4 my-8">
    {#each polls as poll}
        <Poll {poll} on:vote={handleVote} />
    {/each}
</main>

<style>
    
</style>