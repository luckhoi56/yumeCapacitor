<script>
  import YumeCard from "../components/YumeCard.svelte";

  export let name;
  let m_newest_order = ""
  setInterval(function(){
    onButtonTap()
}, 10000) //every 10 seconds auto run
  let m_filtered_orders = [];
  async function onButtonTap() {
    const response = await fetch("http://localhost:4242/getOrder");

    let order_queue = await response.json();

    let filtered_order_queue = order_queue;
    for (let order of filtered_order_queue) {
      order.content = filterOrder(order.content);
	}
	m_filtered_orders = filtered_order_queue
  //console.log()
  if (m_filtered_orders.length > 0 && m_newest_order ==""){
    m_newest_order = m_filtered_orders[m_filtered_orders.length -1].orderNumber
    document.querySelector("audio").play();
    console.log("tap first received")
  }
  if(m_newest_order != "" && m_newest_order != m_filtered_orders[m_filtered_orders.length -1].orderNumber){ // new order received and the newest is not blank
    document.querySelector("audio").play();
    m_newest_order = m_filtered_orders[m_filtered_orders.length -1].orderNumber
    console.log("tap inside")
    console.log(m_newest_order)
  }
  
  
  
  }

  function filterOrder(orders_queue) {
    let m_items = [];

    for (let item of orders_queue) {
      if (item.Quantity > 0) m_items.push(item);
    }
    return m_items;
  }
  //sound
  

function playAudio() { 
  console.log("play is clicked")
   document.querySelector("audio").play(); 
} 

function pauseAudio() { 
   document.querySelector("audio").pause(); 
} 
</script>

<style>

  
</style>

<main>
  <h1>Order cua Khach Hang!</h1>
  <button text="tap me now" on:click={onButtonTap}>Tap Me</button>
  {#each m_filtered_orders as order}
    <YumeCard m_items={order.content} order_number={order.orderNumber}/>
    
  {/each}

</main>

<audio id="myAudio">
  
  <source src="https://yumemenu.s3-us-west-1.amazonaws.com/sound/yukaay.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

<p>Click the buttons to play or pause the audio.</p>

<button on:click={playAudio} type="button">Play Audio</button>
<button on:click={pauseAudio} type="button">Pause Audio</button> 
