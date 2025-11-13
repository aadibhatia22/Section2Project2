<script lang="ts">
    

    let Celcius:number | null = $state(null);
    let Farenheit: number =   $derived(Math.pow((9 / 5) * (Celcius ?? 0) + 32, Celcius === null ? 0 : 1));

    $effect( ()=>{

        console.log(`Celcius: ${Celcius}, Farenheit: ${Farenheit}`);

    })


</script>

<div class = "flex gap-4 items-center mt-4">
    <input type="text" placeholder="Enter Temperature:" bind:value={Celcius}>
    <p>{Farenheit}</p>

</div>