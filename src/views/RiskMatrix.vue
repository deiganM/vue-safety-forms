<template>
  <div class="main-container">
    <div>
      <h2>Is the following task considered high risk?</h2>
      <div class="risk-question-container">
        <div class="radio-group">
          <div class="radio-buttons">
            <input type="radio" id="no" name="high-risk-question" value="no">
            <label for="no">No</label>
          </div>
          <div class="radio-buttons">
            <input type="radio" id="yes" name="high-risk-question" value="yes">
            <label for="yes">Yes</label>
          </div>
        </div>
      </div>
      <div v-if="showRiskMatrix">
        <risk-matrix-table />
      </div>
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
      showRiskMatrix: true
    }
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
</style>
