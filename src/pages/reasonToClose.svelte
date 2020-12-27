<script>
  import { Button, TextArea } from "carbon-components-svelte";
  async function sendReasonToClose() {
    const res = await fetch("http://192.168.43.61:4242/postReasonToClose", {
      headers: {
        "Content-Type": "application/json"
      },
      method: "POST",
      body: JSON.stringify({
        reason: document.querySelector("TextArea").value
      })
    });
    document.querySelector("TextArea").value = "";
  }
</script>

<style>

</style>

<main>
  <TextArea
    labelText="App description"
    placeholder="Enter a description..."
     />
  <Button on:click={sendReasonToClose}>Send</Button>
</main>
