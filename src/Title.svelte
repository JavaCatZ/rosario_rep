<script>
    export let name;
</script>

<style>
	#name {
        margin: 1rem;  
        width: 38rem;
        color: #330033;
        font-size: 1.5rem;
    }

     @media (max-width: 320px) {
        #name {
            width: 18rem;
        }
     }
</style>

<h4 id = "name">{ name }</h4>