<template>
  <div>
    <label for="word">Search for Definition</label>

    <input
      v-model="typedWord"
      type="search"
      id="word"
      name="word"
      placeholder="Type Word Here"
    />
    <p>Definition for Word: {{ typedWord }}</p>
    <button @click="getDefinition">search</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "WordInput",
  data() {
    return {
      typedWord: "",
      wordDefinition: [],
    };
  },
  methods: {
    async getDefinition() {
      try {
        const response = await axios.get(
          `https://www.dictionaryapi.com/api/v3/references/collegiate/json/${this.typedWord}?key=dde18990-3467-4b26-bb9f-c8217de8b929`
        );
        this.wordDefinition = response.data;
      } catch (error) {
        console.error(error);
      }
    },
  },
};
// User Types word in search bar
// Press Search
// Make a request https://www.dictionaryapi.com/api/v3/references/collegiate/json/joyful?key=dde18990-3467-4b26-bb9f-c8217de8b929

// Now that we have the data what do we want to do with it: A. Display it and styled B. Data Properties Displayed
</script>
