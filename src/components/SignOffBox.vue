<template>
  <div>
    <div class="sign-off-box">
      <p>Approval required from: <span class="approver-name">{{ approver }}</span></p>
      <div>
        <div class="form-section">
          <div>
            <label for="approver-name">Name</label>
            <input type="text" name="approver-name">
          </div>
            <label for="company-division">Company Division</label>
            <input type="text" name="company-division">
        </div>
        <div class="form-section">
          <label for="approval-date">Date</label>
          <input type="text" name="approval-date">
          <label for="approval-select">Approved</label>
          <select name="approval-select">
            <option value="">--Please choose an option--</option>
            <option value="no">No</option>
            <option value="yes">Yes</option>
          </select>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SignOffCard',
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
  /* height: 20vh; */
  margin: 0 auto;
  /* display: flex;
  justify-content: center;
  align-items: center; */
}

.approver-name {
  font-weight: bold;
}

.form-section {
  border: solid lime 1px;
  display: flex;
  justify-content: space-between;
}
</style>