<script>
  export let redAutoScore = "--";
  export let redTeleopScore = "--";
  export let redEndgameScore = "--";
  export let redFouls = "--";
  export let redTotalScore = "--";
  export let blueAutoScore = "--";
  export let blueTeleopScore = "--";
  export let blueEndgameScore = "--";
  export let blueFouls = "--";
  export let blueTotalScore = "--";


  const redWins = redTotalScore > blueTotalScore;

</script>




<div class="flex justify-center mt-4">
<table class= "text-sm text-center border-collapse" style="width: 900px">
  <thead>
    <tr class="bg-yellow-200">
      <th class="px-4 py-2 border">Alliance</th>
      <th class="px-4 py-2 border">Auto Score</th>
      <th class="px-4 py-2 border">Teleop Score</th>
      <th class="px-4 py-2 border">Endgame Score</th>
      <th class="px-4 py-2 border">Fouls</th>
      <th class="px-4 py-2 border">Total Score</th>
    </tr>
  </thead>

  <tbody>
    <tr class="bg-red-100" class:boldText={redWins}>
      <td class="px-4 py-2 border ">Red</td>
      <td class="px-4 py-2 border">{redAutoScore}</td>
      <td class="px-4 py-2 border">{redTeleopScore}</td>
      <td class="px-4 py-2 border">{redEndgameScore}</td>
      <td class="px-4 py-2 border">{redFouls}</td>
      <td class="px-4 py-2 border">{redTotalScore}</td>
    </tr>

    <tr class="bg-blue-100">
      <td class="px-4 py-2 border text-blue-600" class:boldText={!redWins}>Blue</td>
      <td class="px-4 py-2 border">{blueAutoScore}</td>
      <td class="px-4 py-2 border">{blueTeleopScore}</td>
      <td class="px-4 py-2 border">{blueEndgameScore}</td>
      <td class="px-4 py-2 border">{blueFouls}</td>
      <td class="px-4 py-2 border text-blue-600 ">{blueTotalScore}</td>
    </tr>
  </tbody>
</table>
</div>


<style>
  .boldText {
    font-weight: 700;
  }
</style>