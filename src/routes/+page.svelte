<script>
  import MatchCard from '$lib/components/MatchCard.svelte';
    let eventCode = "";
    let errorMessage = "";

    let matchObjectArray = [];

    async function fetchFromAPI(eventCode){
        const res = await fetch(`https://api.statbotics.io/v3/matches?event=${eventCode}`);
        if(!res.ok){
            throw new Error(`Error: ${res.status} ${res.statusText}`);

        }
        return res.json();
    }

  async function loadMatches() {
    errorMessage = "";
    try {
      matchObjectArray = await fetchFromAPI(eventCode.trim());
      console.log("Matches:", matchObjectArray);
    } catch (err) {
      console.error(err);
      errorMessage = err.message;
    }
  } 


</script>
  {#if errorMessage}
    <div class="mt-4 bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded">
      {errorMessage}
    </div>
  {/if}

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

<style>
  .hoverColorChange {
    transition: opacity 0.25s ease;  
  }

  .hoverColorChange:hover {
    opacity: 0.6;
  }
</style>