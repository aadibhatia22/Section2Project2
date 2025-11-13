<script lang="ts">
    export let color: string = "beige";
    export let textColor: string = "black";
</script>

 
<button style:background-color={color} style:color={textColor} class ="px-4 py-2 text-white rounded">

    <slot>Default Text</slot>

</button>


