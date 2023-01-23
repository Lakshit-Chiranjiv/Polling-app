<script>

</script>

<main>
    <form class="bg-slate-800 my-8 rounded px-12 py-12">
        <div class="flex justify-around items-start py-4 gap-12">
            <div class="flex-1">
                <label for="pollName" class="text-sm text-white">Poll Name</label><br>
                <input type="text" id="pollName" name="pollName" placeholder="Poll Name" class="border-gray-400 outline-0 border rounded text-sm h-12 p-2 w-full mb-4"/>
                <br>
        
                <label for="pollDescription" class="text-sm text-white">Poll Description</label><br>
                <textarea id="pollDescription" name="pollDescription" placeholder="Poll Description" class="border-gray-400 outline-0 border rounded text-sm h-44 p-2 w-full mb-4"/>
                <br>
            </div>

            <div class="flex-1">
                <label for="pollOption1" class="text-sm text-white">Poll Option 1</label><br>
                <input type="text" id="pollOption1" name="pollOption1" placeholder="Poll Option 1" class="border-gray-400 outline-0 border rounded text-sm h-12 p-2 w-full mb-4"/>
                <br>
                <label for="pollOption2" class="text-sm text-white">Poll Option 2</label><br>
                <input type="text" id="pollOption2" name="pollOption2" placeholder="Poll Option 2" class="border-gray-400 outline-0 border rounded text-sm h-12 p-2 w-full mb-4"/>
                <br>
        
                <button type="button" class="text-white bg-orange-500 px-4 py-2 rounded my-4 text-lg font-bold">+</button>
            </div>
        </div>

        <div class="flex justify-center w-full">
            <button type="submit" class="w-[50%] bg-orange-500 text-white py-2 rounded">Create Poll</button>
        </div>
    </form>
</main>