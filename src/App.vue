<template>
  <div>
    <label for="userInput">Enter Text:</label>
    <input v-model="inputText" id="userInput" />
    <button @click="handleSubmit">Submit</button>

    <div v-if="submittedText">
      <p>Submitted Text:</p>
      <p>{{ submittedText }}</p>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const inputText = ref('');
    const submittedText = ref('');

    const handleSubmit = () => {
      submittedText.value = inputText.value;
    };

    return {
      inputText,
      submittedText,
      handleSubmit,
    };
  },
};
</script>
