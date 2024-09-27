<template>
  <button type="submit" class="form-button" @click="submitForm">Submit</button>
</template>

<script>
export default {
  methods: {
    submitForm() {
      this.$emit('custom-submit')
    }
  }
}
</script>

<style scoped>
.form-button {
  background-color: #4caf50;
  color: #fff;
  padding: 10px 15px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin-top: 2rem;
}

.form-button:hover {
  background-color: #45a049;
}
</style>
