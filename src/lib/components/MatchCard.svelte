<script>
  import MatchInfo from '$lib/components/MatchInfo.svelte';
  import ScoreTable from '$lib/components/ScoreTable.svelte';
  import AllianceTable from '$lib/components/AllianceTable.svelte';
  import VideoEmbed from '$lib/components/VideoEmbed.svelte'

  export let match;

</script>
<MatchInfo 
  matchKey={match.key}
  matchName={match.match_name}

/>

<ScoreTable 
  redAutoScore={match.result.red_auto_points}
  redTeleopScore={match.result.red_teleop_points}
  redEndgameScore={match.result.red_endgame_points}
  redFouls={match.result.red_score - match.result.red_no_foul}
  redTotalScore={match.result.red_score}

  blueAutoScore={match.result.blue_auto_points}
  blueTeleopScore={match.result.blue_teleop_points}
  blueEndgameScore={match.result.blue_endgame_points}
  blueFouls={match.result.blue_score - match.result.blue_no_foul}
  blueTotalScore={match.result.blue_score}



/>

<div class="mt-10 flex justify-center">
  <div class="flex gap-20 items-start">
    <AllianceTable 
      redTeams = {match.alliances.red.team_keys}
      blueTeams = {match.alliances.blue.team_keys}
    
    />
    <VideoEmbed 
    
      videoId = {match.video}
    />
  </div>
</div>
<div class="mb-10"></div>