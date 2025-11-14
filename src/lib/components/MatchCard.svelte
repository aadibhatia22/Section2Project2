<script>
  import MatchInfo from '$lib/components/MatchInfo.svelte';
  import ScoreTable from '$lib/components/ScoreTable.svelte';
  import AllianceTable from '$lib/components/AllianceTable.svelte';
  import VideoEmbed from '$lib/components/VideoEmbed.svelte'
</script>
<MatchInfo />
<ScoreTable />

<div class="mt-10 flex justify-center">
  <div class="flex gap-20 items-start">
    <AllianceTable />
    <VideoEmbed />
  </div>
</div>