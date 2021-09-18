<template>
  <div>
    <h1>This is an about page</h1>
    <div class="wrapper">
      <div>
        Lorem ipsum dolor sit.
      </div>
      <div>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque, aperiam! Culpa deserunt iste ipsum, consequatur consequuntur soluta nam mollitia laboriosam totam quibusdam nisi facere repudiandae. Perspiciatis culpa at earum illo unde, asperiores facilis voluptatem dolore voluptatibus fugit quia commodi iste.
      </div>
      <div class="nested">
        <div>lorem</div>
        <div>lorem</div>
        <div>lorem</div>
      </div>
      <div>
        Lorem ipsum dolor sit.
      </div>
      <div>
        Lorem ipsum dolor sit.
      </div>
      <div>
        Lorem ipsum dolor sit.
      </div>
      <div>
        Lorem ipsum dolor sit.
      </div>
    </div>
  </div>
</template>

<style scoped>
  .wrapper {
    display: grid;
    /* grid-template-columns: 1fr 1fr 1fr; */
    grid-template-columns: repeat(3, 1fr);
    /* grid-template-columns: repeat(4, 1fr 2fr); */
    /* column-gap: 1em;
    row-gap: 1em; */
    grid-gap: 1em;
    /* grid-auto-rows: 100px; */

    /* 100px by default, but will expand to fit content  */
    grid-auto-rows: minmax(100px, auto);
  }

  .nested {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 70px;
    grid-gap: 1em;
  }

  .wrapper > div {
    background: #eee;
    padding: 1em;
  }

  .wrapper > div:nth-child(odd) {
    background: #ddd;
  }

  .nested > div {
    border: solid 1px #333;
    padding: 1em;
  }
</style>
