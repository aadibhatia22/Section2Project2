<script lang="ts">
    let buttonText: string = "Click Me"
</script>
<button class = "btn">{buttonText}</button>
<style>
    .btn{
        font-family: 'Courier New', Courier, monospace;
        color:white;
        background-color: black;
        width: 100px;
        height: 45px;
        border-radius: 10%;
        border: 0px solid tan;
       
    }
    .btn:hover{
        opacity: 0.83;
    }
    .btn:active{
        opacity: 0.5;
    }
        
    


</style>