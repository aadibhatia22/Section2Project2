<script>
    import MatchCard from '$lib/components/MatchCard.svelte';
	import Layout from './+layout.svelte';
    let eventCode = "";


    let matchObjectArray = [];

    async function fetchFromAPI(eventCode){
        const res = await fetch(`https://api.statbotics.io/v3/event/${eventCode}/matches`);
        if(!res.ok){
            throw new Error(`Error: ${res.status} ${res.statusText}`);

        }
        return res.json();
    }

    async function loadMatches(){

       
        matchObjectArray = await fetchFromAPI(eventCode);
    console.log("Matches:", matchObjectArray);
    }


</script>


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