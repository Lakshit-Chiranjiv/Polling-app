<script>

</script>

<main>
    <form>
        <div class="flex justify-around items-center">
            <div>
                <label for="pollName">Poll Name</label>
                <input type="text" id="pollName" name="pollName" placeholder="Poll Name"/>
        
                <label for="pollDescription">Poll Description</label>
                <textarea id="pollDescription" name="pollDescription" placeholder="Poll Description"/>
            </div>

            <div>
                <label for="pollOption1">Poll Option 1</label>
                <input type="text" id="pollOption1" name="pollOption1" placeholder="Poll Option 1"/>
                <label for="pollOption2">Poll Option 2</label>
                <input type="text" id="pollOption2" name="pollOption2" placeholder="Poll Option 2"/>
        
                <button type="button">Add Another Option</button>
            </div>
        </div>

        <button type="submit">Submit</button>
    </form>
</main>