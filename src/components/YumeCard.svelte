<script>
  import { Tile, Button } from "carbon-components-svelte";
  import { Grid, Row, Column } from "carbon-components-svelte";
  import DetailButton from "./DetailButton.svelte";
</script>

<style>

</style>

<main>
  <Tile>
    <Grid>
      <Row>
        <Column style="text-align:center">OrderNumber</Column>
      </Row>
      <br>
      <Row>
        <Column style="text-align:center">Customer Name</Column>
      </Row>
      <br>
      <Row>
        <Column style="text-align:left">
          <DetailButton m_content={"I dont know"}></DetailButton>  
        </Column>
        <Column style="text-align:right" >
          <Button  size="small"  kind="tertiary">San Sang</Button>
          
        </Column>
      </Row>
    </Grid>
  </Tile>


  <br>
 

</main>
