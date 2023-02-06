<script>
    import { createEventDispatcher } from "svelte";
    import PollStore from "../stores/PollStore";

    const dispatch = createEventDispatcher();

    let pollName = "";
    let pollDescription = "";
    let pollOptions = ['','']
    let error = ''
    let showError = false

    const formSubmitHandler = () => {
        if(pollName === '' || pollDescription === '' || pollOptions.includes('')) {
            if(pollName === '') {
                error = 'Poll Name is required'
            }
            else if(pollDescription === '') {
                error = 'Poll Description is required'
            }
            else if(pollOptions.includes('')) {
                error = 'Poll Options are required'
            }
            showError = true
            return
        }
        else{
            error = ''
            showError = false
            console.log(pollName, pollDescription, pollOptions);
            PollStore.update(polls => {
                return [...polls, {
                    id: (polls.length + 1).toString(),
                    question: pollName,
                    description: pollDescription,
                    options: pollOptions,
                    votes: pollOptions.map(() => 0),
                    pollTimeLeft: 1000
                }]
            })
            pollName = ''
            pollDescription = ''
            pollOptions = ['','']
            dispatch('pollCreated')
        }
    }
</script>

<main>
    <form class="bg-slate-800 my-12 rounded px-12 py-12" on:submit|preventDefault={formSubmitHandler}>
        <h1 class="text-3xl font-bold mb-4 text-white">Create Poll</h1>
        <div class="flex justify-around items-start py-4 gap-12">
            <div class="flex-1">
                <label for="pollName" class="text-sm text-white">Poll Name</label><br>
                <input type="text" id="pollName" name="pollName" placeholder="Poll Name" class="border-gray-400 outline-0 border rounded text-sm h-12 p-2 w-full mb-4" bind:value={pollName}/>
                <br>
        
                <label for="pollDescription" class="text-sm text-white">Poll Description</label><br>
                <textarea id="pollDescription" name="pollDescription" placeholder="Poll Description" class="border-gray-400 outline-0 border rounded text-sm h-44 p-2 w-full mb-4" bind:value={pollDescription}/>
                <br>
            </div>

            <div class="flex-1">
                <label for="pollOptions" class="text-sm text-white">Poll Options</label><br>
                {#each pollOptions as option, i}
                    <input type="text" id="pollOptions" name="pollOptions" placeholder="Poll Option" class="border-gray-400 outline-0 border rounded text-sm h-12 p-2 w-full mb-4" bind:value={pollOptions[i]}/>
                {/each}
        
                <button type="button" class="text-white bg-orange-500 px-4 py-2 rounded my-4 text-lg font-bold" on:click={() => pollOptions = [...pollOptions, '']}>
                    +
                </button>
            </div>
        </div>

        {#if showError}
            <div class="bg-red-500 text-white text-center p-4 rounded mb-4">
                {error}
            </div>
        {/if}

        <div class="flex justify-center w-full">
            <button type="submit" class="w-[50%] bg-orange-500 text-white py-2 rounded">Create Poll</button>
        </div>
    </form>
</main>