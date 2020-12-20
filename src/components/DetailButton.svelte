<script>
  import { Button, Modal } from "carbon-components-svelte";
    export let m_content=""
    export 
  let open = false;
</script>

<Button size="small" kind="tertiary" on:click={() => (open = true)}>
  Chi Tiet
</Button>

<Modal
  bind:open
  modalHeading="Chi Tiet"
  
  secondaryButtonText="Ok"
  on:click:button--secondary={() => (open = false)}
  on:open
  on:close
  on:submit>
  <p>{m_content}</p>
</Modal>
