<script>
  import Poll from "./Poll.svelte";

    export let polls = [
        {
            question: "What is your favorite color?",
            description: "This is a description of the poll",
            options: ["Red", "Blue", "Green", "Yellow"]
        },
        {
            question: "What is your favorite animal?",
            description: "This is a description of the poll",
            options: ["Dog", "Cat", "Bird", "Fish"]
        },
        {
            question: "What is your favorite food?",
            description: "This is a description of the poll",
            options: ["Pizza", "Burger", "Tacos", "Salad"]
        },
        {
            question: "What is your favorite drink?",
            description: "This is a description of the poll",
            options: ["Water", "Soda", "Juice", "Milk"]
        },
        {
            question: "What is your favorite movie?",
            description: "This is a description of the poll",
            options: ["Star Wars", "Harry Potter", "Lord of the Rings", "The Matrix"]
        },
        {
            question: "What is your favorite TV show?",
            description: "This is a description of the poll",
            options: ["The Office", "Friends", "Breaking Bad", "Game of Thrones"]
        },
        {
            question: "What is your favorite video game?",
            description: "This is a description of the poll",
            options: ["Minecraft", "Fortnite", "Call of Duty", "League of Legends"]
        },
        {
            question: "What is your favorite sport?",
            description: "This is a description of the poll",
            options: ["Basketball", "Football", "Baseball", "Soccer"]
        },
        {
            question: "What is your favorite season?",
            description: "This is a description of the poll",
            options: ["Spring", "Summer", "Fall", "Winter"]
        },
        {
            question: "What is your favorite holiday?",
            description: "This is a description of the poll",
            options: ["Christmas", "Thanksgiving", "Halloween", "New Years"]
        },
        {
            question: "What is your favorite fruit?",
            description: "This is a description of the poll",
            options: ["Apple", "Banana", "Orange", "Strawberry"]
        },
        {
            question: "What is your favorite vegetable?",
            description: "This is a description of the poll",
            options: ["Carrot", "Broccoli", "Potato", "Tomato"]
        },
        {
            question: "What is your favorite candy?",
            description: "This is a description of the poll",
            options: ["Sour Patch Kids", "Skittles", "M&Ms", "Reese's"]
        },
        {
            question: "What is your favorite ice cream flavor?",
            description: "This is a description of the poll",
            options: ["Vanilla", "Chocolate", "Strawberry", "Mint Chocolate Chip"]
        },
    ]
</script>

<main class="grid grid-cols-2 gap-4 my-8">
    {#each polls as poll}
        <Poll {poll} />
    {/each}
</main>

<style>
    
</style>