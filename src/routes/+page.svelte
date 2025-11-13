<script lang="ts">
    import Button from "$lib/components/Button.svelte"
    import Counter from "$lib/components/Counter.svelte"
    import NewButton from "$lib/components/NewButton.svelte"
    import TemperatureConverter from "$lib/components/TemperatureConverter.svelte"
</script>


<div class = "flex gap-4 items-center mt-4 justify-center">
    <Button />
    <Counter />
    <Counter />
    <NewButton color="Maroon" textColor="white">Testing</NewButton>
    <NewButton />
    <TemperatureConverter />

</div>