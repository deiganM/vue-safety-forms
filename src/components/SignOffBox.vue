<template>
  <div>
    <div class="sign-off-box">
      <p>Approval required from: <span class="approver-name">{{ approver }}</span></p>
      <div>
        <div class="form-section">
          <div class="name-comp">
            <md-field class="sign-off-input">
              <label>Name</label>
              <md-input></md-input>
            </md-field>
            <md-field class="sign-off-input">
              <label>Company Division</label>
              <md-input></md-input>
            </md-field>
          </div>
        </div>
        <div class="form-section">
          <div class="name-comp">
            <md-field class="sign-off-input">
              <label>Name</label>
              <md-input></md-input>
            </md-field>
            <md-field class="sign-off-input">
              <label>Company Division</label>
              <md-input></md-input>
            </md-field>
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

    }
  },
  props: {
    approver: {
      type: String,
      required: true,
      default: () => 'On shift Supervisor'
    }
  },
  // computed: {
  //   fullText() {
  //     return this.approver + 'Full Text'
  //   }
  // }
}
</script>

<style scoped>
.sign-off-box {
  background: #71c2e2;
  font-size: 20px;
  width: 80vw;
  border: solid darkslategrey 3px;
  border-radius: 3px;
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

.sign-off-input{
  margin: 1rem 3rem;
}
</style>