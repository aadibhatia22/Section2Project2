<script lang="ts">
    let count = 0
</script>

<button class = "counter" on:click={()=>count++}> {count}</button>

<style>
    .counter{
        background-color: tan;
        color: black;
        border-radius:  15%;
        width: 75px;
        height: 75px;
        transition: opacity 0.2s ease;
    
    }
    .counter:hover{
        opacity: 0.83;
    }
</style>

