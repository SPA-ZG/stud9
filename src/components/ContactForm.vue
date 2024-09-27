<template>
  <h1 class="text-title">Kontaktiraj nas</h1>

  <form ref="form" class="custom-form" @submit.prevent="submitForm">
    <label for="name" class="form-label">Ime:</label>
    <input type="text" id="name" v-model="formData.name" class="form-input" />
    <div v-if="!formData.name" class="error-message">Potrebno upisati ime</div>

    <label for="email" class="form-label">Email:</label>
    <input type="text" id="email" v-model="formData.email" class="form-input" />
    <div v-if="!formData.email" class="error-message">Potrebno upisati email</div>

    <label for="message" class="form-label">Poruka:</label>
    <textarea id="message" v-model="formData.message" class="form-textarea"></textarea>
    <div v-if="!formData.message" class="error-message">Potrebno upisati poruku</div>

    <SubmitButton @custom-submit="submitForm"></SubmitButton>
  </form>
</template>

<script>
import SubmitButton from './SubmitButton.vue'

export default {
  components: {
    SubmitButton
  },
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  computed: {
    isFormValid: function () {
      return this.formData.name !== '' && this.formData.email !== '' && this.formData.message !== ''
    }
  },
  methods: {
    submitForm: function () {
      if (!this.isFormValid) {
      } else {
        console.log('Form submitted:', this.formData)
        this.$refs.form.reset()
        this.formData = {
          name: '',
          email: '',
          message: ''
        }
      }
    }
  }
}
</script>

<style>
form {
  max-width: 400px;
  margin: 0 auto;
}

label {
  display: block;
  margin-top: 1.5rem;
  margin-bottom: 8px;
  font-weight: bold;
}

input,
textarea {
  width: 100%;
  padding: 8px;
  margin-bottom: 16px;
  box-sizing: border-box;
  border: 1px solid #ccc;
  border-radius: 4px;
}

textarea {
  height: 120px;
}

button {
  background-color: #4caf50;
  color: #fff;
  padding: 10px 15px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}

.text-title {
  position: relative;
  font-size: 2rem;
  font-weight: 700;
  color: var(--heading-text-clr);
  font-family: var(--font-family);
  margin-bottom: 1rem;
  text-align: center;
  color: var(--heading-text-clr);
}
</style>
