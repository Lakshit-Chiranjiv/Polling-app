<script>
  import Poll from "./Poll.svelte";
  import PollStore from "../stores/PollStore";
  import { onDestroy } from "svelte";
    let polls = []

    // const unsub = PollStore.subscribe(value => {
    //     polls = value;
    // })

    // const handleVote = (e) => {
    //     const { index, pollId } = e.detail;
    //     let copiedPolls = [...polls];
    //     let upvotedPoll = copiedPolls.find(poll => poll.id === pollId);
    //     upvotedPoll.votes[index]++;
    //     polls = copiedPolls;
    // }

    // onDestroy(() => {
    //     unsub();
    // })
</script>

<main class="grid grid-cols-2 gap-4 my-8">
    {#each $PollStore as poll}
        <Poll {poll} />
    {/each}
</main>

<style>
    
</style>