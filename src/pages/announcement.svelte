<script>
  import { Button, TextArea } from "carbon-components-svelte";
  async function sendAnnouncement() {
    console.log("got clicked")
    const res = await fetch("https://fabubackend.de:4141/postAnnouncement", {
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
  <Button on:click={sendAnnouncement}>Send</Button>
</main>
