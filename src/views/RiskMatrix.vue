<template>
  <div class="main-container">
    <div>
      <h2>Is the following task considered high risk?</h2>
      <div class="risk-question-container">
        <div class="radio-group">
          <div class="radio-buttons">
            <input @click="hideRiskMatrix" type="radio" id="no" name="high-risk-question" value="no">
            <label for="no">No</label>
          </div>
          <div class="radio-buttons">
            <input @click="showRiskMatrix" type="radio" id="yes" name="high-risk-question" value="yes">
            <label for="yes">Yes</label>
          </div>
        </div>
      </div>
      <div v-if="riskMatrix">
        <!-- <risk-matrix-table @custom-event-name="setMessage" /> -->
        <risk-matrix-table @yellow-event="yellowStatus" />
      </div>
      <div class="warning-containers">
        <div class="yellow-container">
          <p class="warning-text">YELLOW STATUS; Level 2 access is required</p>
        </div>
      </div>
      <!-- <p>{{ message }}</p> -->
    </div>
  </div>
</template>

<script>

// @ is an alias to /src
import RiskMatrixTable from '../components/RiskMatrixTable.vue'

export default {
  Name: 'RiskMatrix',
  components: {
    RiskMatrixTable
  },
  data() {
    return {
      riskMatrix: false,
      // message:'Hi',
      yellow: false
    }
  },
  methods: {
    showRiskMatrix() {
      this.riskMatrix = true
    },
    hideRiskMatrix() {
      this.riskMatrix = false
    },
    // Define method that will use the payload to update the data property
    // setMessage(payload) {
    //   this.message = payload.message
    // },
    yellowStatus(payload) {
      this.yellow = payload.yellow
      console.log(this.yellow)
    },
  }
}
</script>
<style scoped>
  .main-container {
    
  }

  .risk-question-container {
    display: flex;
    justify-content: center;
    font-size: 20px;
    margin: 1rem;
    padding: 1rem;
  }

  .radio-group {
    display: flex;
    justify-content: space-between;
    width: 200px;
  }

  label{
    cursor: pointer;
  }

  input[type="radio"] {
    cursor: pointer;
    padding: 2rem;
  }
  
  .warning-containers {
    margin: 3rem;
  }

  .yellow-container {
    background: #ecf00e;
    border: solid darkslategrey 3px;
    border-radius: 3px;
    height: 20vh;
    width: 80vw;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .warning-text {
    font-size: 20px ;
    font-weight: 800;
  }
</style>
