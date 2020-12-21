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
        <Column style="text-align:center">Mã Số</Column>
      </Row>
      <br />
      <Row>
        <Column style="text-align:center">Tên Khách Hàng</Column>
      </Row>
      <br />
      <Row>
        <Column style="text-align:center">
          <DetailButton m_content={'I dont know'} />
        </Column>
      </Row>
      <br />
      <br />
      
      <Row>
        <Column style="text-align:center">
          <Button size="small"  kind="danger" >San Sang</Button>
        </Column>
      </Row>
    </Grid>
  </Tile>

  <br />

</main>
