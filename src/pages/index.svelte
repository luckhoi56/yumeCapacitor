<script>
  import YumeCard from "../components/YumeCard.svelte";
  let m_filtered_orders = [];
  async function onButtonTap() {
    const response = await fetch("http://192.168.43.61:4242/getOrder");

    let order_queue = await response.json();

    let filtered_order_queue = order_queue;
    for (let order of filtered_order_queue) {
      order.content = filterOrder(order.content);
	}
	m_filtered_orders = filtered_order_queue
	//console.log()
  }

  function filterOrder(orders_queue) {
    let m_items = [];

    for (let item of orders_queue) {
      if (item.Quantity > 0) m_items.push(item);
    }
    return m_items;
  }
</script>

<style>

  
</style>

<main>
  <YumeCard></YumeCard>

</main>
