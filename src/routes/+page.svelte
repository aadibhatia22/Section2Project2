<script>
  import MatchCard from '$lib/components/MatchCard.svelte';
    let eventCode = "";
    let errorMessage = "";

    let matchObjectArray = [];
    //makes function to load data from the API
    async function fetchFromAPI(eventCode){
        const res = await fetch(`https://api.statbotics.io/v3/matches?event=${eventCode}`);
        if(!res.ok){
            throw new Error(`Error: ${res.status} ${res.statusText}`);

        }
        return res.json();
    }
  //checks for any errors and passes API data to the matchObjectArray variable
  async function loadMatches() {
    errorMessage = "";
    try {
      matchObjectArray = await fetchFromAPI(eventCode.trim());
      //for checking purposes
      console.log("Matches:", matchObjectArray[0]);
    } catch (err) {
      console.error(err);
      errorMessage = err.message;
    }
  } 


</script>


  <!-- Displaying the errors -->
  {#if errorMessage}
    <div class="mt-4 bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded">
      {errorMessage}
    </div>
  {/if}


<!-- Making the input elements -->
<div class="flex justify-center mt-10 gap-3">
  <input
    bind:value={eventCode}
    placeholder="Enter event code: "
    class="border px-3 py-2 rounded w-64"
  />

  <button
    class="bg-blue-600 text-white px-4 py-2 rounded hoverColorChange"
    on:click={loadMatches}
  >
    Load Matches
  </button>
</div>


<!-- making the matchcards from the API data filled array  -->
{#if matchObjectArray.length > 0}
  {#each matchObjectArray as match}
    <MatchCard {match} />
  {/each}
{/if}
{#if matchObjectArray.length <= 0}
  <div class="mt-4 text-center text-gray-500">
    No matches loaded. Please enter an event code and click "Load Matches".
  </div>
{/if} 




<!-- style for button -->
<style>
  .hoverColorChange {
    transition: opacity 0.25s ease;  
  }

  .hoverColorChange:hover {
    opacity: 0.6;
  }
</style>