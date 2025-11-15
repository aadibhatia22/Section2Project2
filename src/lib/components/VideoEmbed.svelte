<script>
  export let videoId = null;
</script>

<div class="w-[600px] h-[350px] border border-gray-400 bg-gray-50 flex items-center justify-center">
  {#if videoId}
    <iframe
      src={`https://www.youtube.com/embed/${videoId}`}
      allowfullscreen
      class="w-full h-full"
      title={videoId}
    ></iframe>
  {:else}
    <!-- Handels case for no video -->
    <p class="text-gray-500">No video available</p>
  {/if}
</div>
