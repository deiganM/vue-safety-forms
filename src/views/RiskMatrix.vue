<template>
  <div>
    <div class="wrapper">
      <div class="box impact-score">
        Impact Score
      </div>
      <div class="box very-unlikely likelihood">
        Very Unlikely
      </div>
      <div class="box likelihood unlikely">
        Unlikely
      </div>
      <div class="box likelihood possible">
        Possible
      </div>
      <div class="box likelihood likely">
        Likely
      </div>
      <div class="box likelihood highly-likely">
        Highly Likely
      </div>
      <div class="box numbers">
        1
      </div>
      <div class="box numbers">
        2
      </div>
      <div class="box numbers">
        4
      </div>
      <div class="box numbers">
        8
      </div>
      <div class="box numbers">
        16
      </div>
      <div class="box risk-level">
        Catastrophic
      </div>
      <div class="box numbers">
        16
      </div>
      <div class="box yellow">
        16
      </div>
      <div class="box orange">
        32
      </div>
      <div class="box red">
        64
      </div>
      <div class="box red">
        128
      </div>
      <div class="box red">
        256
      </div>
      <div class="box risk-level">
        Major
      </div>
      <div class="box numbers">
        8
      </div>
      <div class="box yellow">
        8
      </div>
      <div class="box yellow">
        16
      </div>
      <div class="box orange">
        32
      </div>
      <div class="box red">
        64
      </div>
      <div class="box red">
        128
      </div>
      <div class="box risk-level">
        Significant
      </div>
      <div class="box numbers">
        4
      </div>
      <div class="box green">
        4
      </div>
      <div class="box yellow">
        8
      </div>
      <div class="box yellow">
        16
      </div>
      <div class="box orange">
        32
      </div>
      <div class="box red">
        64
      </div>
      <div class="box risk-level">
        Minor
      </div>
      <div class="box numbers">
        2
      </div>
      <div class="box green">
        2
      </div>
      <div class="box green">
        4
      </div>
      <div class="box yellow">
        8
      </div>
      <div class="box yellow">
        16
      </div>
      <div class="box orange">
        32
      </div>
      <div class="box risk-level">
        insignificant
      </div>
      <div class="box numbers">
        1
      </div>
      <div class="box green">
        1
      </div>
      <div class="box green">
        2
      </div>
      <div class="box green">
        4
      </div>
      <div class="box yellow">
        8
      </div>
      <div class="box yellow">
        16
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
  .wrapper {
    display: grid;
    grid-template-columns: .5fr .5fr 1fr 1fr 1fr 1fr 1fr;
    grid-auto-rows: minmax(5rem, auto);
		border: solid black 2px;
		grid-gap: 2px;
		background: black;
    border-radius: 2px;
    margin: 1rem;
  }
	
  .box {
    display: grid;
    justify-items: center;
    align-items: center;
    padding: .5rem;
  }

  .impact-score {
    background: #d6d6d6;
    color: black;
    font-weight: bold;
    grid-column: 1/3;
    grid-row: 1/3;
  }

  .likelihood {
    background: rgb(243, 237, 171);
    font-weight: bold;
  }

  .very-unlikely {
    grid-column: 3/4;
    grid-row: 1;
  }

  .unlikely {
    grid-column: 4/5;
    grid-row: 1;
  }

  .possible {
    grid-column: 5/6;
    grid-row: 1;
  }

  .likely {
    grid-column: 6/7;
    grid-row: 1;
  }

  .highly-likely {
    grid-column: 7/8;
    grid-row: 1;
  }

  .numbers {
    background: darkslategrey;
    color: whitesmoke;
    font-weight: bold;
  }

	.risk-level {
		background: #d6d6d6;
    color: black;
    font-weight: bold;
	}

  .green {
    background: #62d187;
  }

	.yellow {
		background: #fdff00;
		color: black
	}

	.orange {
		background: #ffa500;
		color: black;
	}

	.red {
		background: rgb(235, 13, 13);
    color: white;
	}
</style>