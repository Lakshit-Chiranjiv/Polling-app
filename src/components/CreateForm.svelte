<script>

</script>

<main>
    <form>
        <div class="flex justify-around items-center">
            <div>
                <label for="pollName" class="text-sm">Poll Name</label><br>
                <input type="text" id="pollName" name="pollName" placeholder="Poll Name" class="border-gray-400 outline-0 border rounded text-sm h-8 p-2"/>
                <br>
        
                <label for="pollDescription" class="text-sm">Poll Description</label><br>
                <textarea id="pollDescription" name="pollDescription" placeholder="Poll Description" class="border-gray-400 outline-0 border rounded text-sm h-20 p-2"/>
                <br>
            </div>

            <div>
                <label for="pollOption1" class="text-sm">Poll Option 1</label><br>
                <input type="text" id="pollOption1" name="pollOption1" placeholder="Poll Option 1" class="border-gray-400 outline-0 border rounded text-sm h-8 p-2"/>
                <br>
                <label for="pollOption2" class="text-sm">Poll Option 2</label><br>
                <input type="text" id="pollOption2" name="pollOption2" placeholder="Poll Option 2" class="border-gray-400 outline-0 border rounded text-sm h-8 p-2"/>
                <br>
        
                <button type="button">Add Another Option</button>
            </div>
        </div>

        <button type="submit">Submit</button>
    </form>
</main>