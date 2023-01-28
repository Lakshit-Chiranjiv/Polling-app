<script>
  import Poll from "./Poll.svelte";

    export let polls = [
        {
            id: '1',
            question: "What is your favorite color?",
            description: "This is a description of the poll",
            options: ["Red", "Blue", "Green", "Yellow"],
            votes: [0, 20, 30, 40],
            pollTimeLeft: 1000,
        },
        {
            id: '2',
            question: "What is your favorite animal?",
            description: "This is a description of the poll",
            options: ["Dog", "Cat", "Bird", "Fish"],
            votes: [10, 20, 30, 40],
            pollTimeLeft: 1000,
        },
        {
            id: '3',
            question: "What is your favorite food?",
            description: "This is a description of the poll",
            options: ["Pizza", "Burger", "Sandwich", "Pasta"],
            votes: [10, 20, 30, 40],
            pollTimeLeft: 1000,
        },
        {
            id: '4',
            question: "What is your favorite drink?",
            description: "This is a description of the poll",
            options: ["Coke", "Pepsi", "Sprite", "Fanta"],
            votes: [10, 20, 30, 40],
            pollTimeLeft: 1000,
        },
        {
            id: '5',
            question: "What is your favorite fruit?",
            description: "This is a description of the poll",
            options: ["Apple", "Orange", "Banana", "Grapes"],
            votes: [10, 20, 30, 40],
            pollTimeLeft: 1000,
        },
        {
            id: '6',
            question: "What is your favorite movie?",
            description: "This is a description of the poll",
            options: ['"The Shawshank Redemption"', '"The Godfather"', '"The Godfather: Part II"', '"The Dark Knight"'],
            votes: [10, 20, 30, 40],
            pollTimeLeft: 1000,
        }
    ]

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