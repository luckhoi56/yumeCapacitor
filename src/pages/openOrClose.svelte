<script>
    import { Tile, Button } from "carbon-components-svelte";
    let m_status ="N/A"
    async function open(){
        const response = await fetch("http://192.168.43.61:4242/openRestaurant")
       // let data = await response.json()
    }

    async function close(){
        const response = await fetch("http://192.168.43.61:4242/closeRestaurant")
    }

    async function checkStatus(){
        const response = await fetch("http://192.168.43.61:4242/statusRestaurant")
        let data = await response.json();
        //checkStatus = status.status
        if(data.status == false)
            m_status ="Closed"
        else
            
            m_status ="Opened"
    }
</script>


<main>
    <Button on:click={open}>Mo Cua </Button>
    <Button on:click={close}>Dong Cua</Button>
    <br>
    <Button on:click={checkStatus}>{m_status}</Button>

</main>

<style>

</style>