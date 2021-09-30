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
        <risk-matrix-table 
          @yellow-event="yellowStatus" 
          @green-event="greenStatus" 
          @orange-event="orangeStatus" 
          @red-event="redStatus"
        />
      </div>
      <div v-if="riskMatrix">
        <div v-if="green" class="warning-containers">
          <div class="green-container">
            <p class="warning-text">GREEN STATUS: Level 1 access is required</p>
          </div>
          <md-button @click="clearButton" class="md-raised md-primary clear-button">Clear risk matrix</md-button>
          <sign-off-box :approver="approver[0]" />
        </div>
        <div v-if="yellow" class="warning-containers">
          <div class="yellow-container">
            <p class="warning-text">YELLOW STATUS: Level 2 access is required</p>
          </div>
          <md-button @click="clearButton" class="md-raised md-primary clear-button">Clear risk matrix</md-button>
          <sign-off-box :approver="approver[0]" />
          <sign-off-box :approver="approver[1]" />
        </div>
        <div v-if="orange" class="warning-containers">
          <div class="orange-container">
            <p class="warning-text">ORANGE STATUS: Level 3 access is required</p>
          </div>
          <md-button @click="clearButton" class="md-raised md-primary clear-button">Clear risk matrix</md-button>
          <sign-off-box  :approver="approver[0]"/>
          <sign-off-box  :approver="approver[1]"/>
          <sign-off-box  :approver="approver[2]"/>
        </div>
        <div v-if="red" class="warning-containers">
          <div class="red-container">
            <p class="red-warning-text">RED STATUS: Level 4 access is required</p>
          </div>
          <md-button @click="clearButton" class="md-raised md-primary clear-button">Clear risk matrix</md-button>
          <sign-off-box  :approver="approver[0]"/>
          <sign-off-box  :approver="approver[1]"/>
          <sign-off-box  :approver="approver[2]"/>
          <sign-off-box  :approver="approver[3]"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import RiskMatrixTable from '../components/RiskMatrixTable.vue'
import SignOffBox from '../components/SignOffBox.vue'

export default {
  Name: 'RiskMatrix',
  components: {
    RiskMatrixTable,
    SignOffBox
  },
  data() {
    return {
      approver: ['Teammate working on task','Shift Supervisor', 'Foreperson', 'Project Manager',],
      riskMatrix: false,
      green: false,
      yellow: false,
      orange: false,
      red:false
    }
  },
  methods: {
    showRiskMatrix() {
      this.riskMatrix = true
    },
    hideRiskMatrix() {
      this.riskMatrix = false,
      this.clearButton()
    },
    yellowStatus(payload) {
      this.yellow = payload.yellow
      this.green = false
      this.orange = false
      this.red = false
    },
    greenStatus(payload) {
      this.green = payload.green
      this.yellow = false
      this.orange = false
      this.red = false
    },
    orangeStatus(payload) {
      this.orange = payload.orange
      this.green = false
      this.yellow = false
      this.red = false
    },
    redStatus(payload) {
      this.red = payload.red
      this.green = false
      this.yellow = false
      this.orange = false
    },
    clearButton() {
      this.yellow = false
      this.green = false
      this.orange = false
      this.red = false
    },
  }
}
</script>
<style scoped>
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

  .green-container {
    background: #0ef06c;
    border: solid darkslategrey 1px;
    border-radius: 3px;
    height: 20vh;
    width: 80vw;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .yellow-container {
    background: #ecf00e;
    border: solid darkslategrey 1px;
    border-radius: 3px;
    height: 20vh;
    width: 80vw;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .orange-container {
    background: #f5d107;
    border: solid darkslategrey 1px;
    border-radius: 3px;
    height: 20vh;
    width: 80vw;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .red-container {
    background: #eb0d0d;
    border: solid darkslategrey 1px;
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

  .red-warning-text {
    font-size: 20px ;
    font-weight: 800;
    color: white;
  }

  .clear-button {
    margin: 2rem;
  }
</style>
