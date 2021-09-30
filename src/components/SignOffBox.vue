<template>
  <div>
    <div class="sign-off-box">
      <p>Approval required from: <span class="approver-name">{{ approver }}</span></p>
      <div>
        <div class="form-section">
          <div class="name-comp">
            <md-field>
              <label>Name</label>
              <md-input></md-input>
            </md-field>
            <md-field>
              <label>Company Division</label>
              <md-input></md-input>
            </md-field>
          </div>
        </div>
        <div class="form-section">
          <div class="name-comp">
            <md-datepicker v-model="selectedDate">
              <label>Select date</label>
            </md-datepicker>

            <div>
              <md-field>
                <label for="field-area">Field Area</label>
                <md-select name="field-area" id="fieldArea">
                  <md-option value="southern-alberta">Southern Alberta</md-option>
                  <md-option value="east-kootenay">East Kootenay</md-option>
                  <md-option value="west-kootenay">West Kootenay</md-option>
                </md-select>
              </md-field>
            </div>

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SignOffCard',
  data() {
    return {
      selectedDate: null
    }
  },
  props: {
    approver: {
      type: String,
      required: true,
      default: () => 'On shift Supervisor'
    }
  },
}
</script>

<style scoped>
.sign-off-box {
  background: #70f77794;
  font-size: 20px;
  width: 80vw;
  border: solid darkslategrey 1px;
  border-radius: 1px;
  margin: 3rem auto;
}

.approver-name {
  font-weight: bold;
}

.form-section {
  display: flex;
  justify-content: space-evenly;
}

.name-comp {
  display: flex;
}
</style>