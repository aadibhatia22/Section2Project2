
<script>
  //getting API data and making default vals
  export let redTeams = ["--", "--", "--"];
  export let blueTeams = ["--", "--", "--"];

</script>

<!-- Making the table, note that the API gives the team names in an array-->
<table class="mx-auto border-collapse text-center font-bold text-black ">
  <tbody>
    <tr>
      <td class="px-6 py-2 bg-red-200">{redTeams[0]}</td>
      <td class="px-6 py-2 bg-blue-200">{blueTeams[0]}</td>
    </tr>
    <tr>
      <td class="px-6 py-2 bg-red-300">{redTeams[1]}</td>
      <td class="px-6 py-2 bg-blue-300">{blueTeams[1]}</td>
    </tr>
    <tr>
      <td class="px-6 py-2 bg-red-400">{redTeams[2]}</td>
      <td class="px-6 py-2 bg-blue-400">{blueTeams[2]}</td>
    </tr>
  </tbody>
</table>