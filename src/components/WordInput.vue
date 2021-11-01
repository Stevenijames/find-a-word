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
    <button @click="resetSearch">Reset</button>
    <p>Definition for Word: {{ typedWord }}</p>
    <button @click="getDefinition">search</button>
    <section
      class="definition"
      v-for="definition in wordDefinitions"
      :key="definition.uuid"
    >
      {{ definition.word }}, {{ definition.partOfSpeech }}
      <ul>
        <li
          v-for="shortDefinition in definition.shortDefinitions"
          :key="shortDefinition"
        >
          {{ shortDefinition }}
        </li>
      </ul>
    </section>
    <p>{{ numsArray[0] }}</p>
    <p v-for="abc in numsArray" :key="abc">
      {{ abc }}
    </p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "WordInput",
  data() {
    return {
      typedWord: "",
      wordDefinitions: [],
      numsArray: [1, 4, 10, 11],
    };
  },
  methods: {
    async getDefinition() {
      try {
        const response = await axios.get(
          `https://www.dictionaryapi.com/api/v3/references/collegiate/json/${this.typedWord}?key=dde18990-3467-4b26-bb9f-c8217de8b929`
        );
        const responseData = response.data;
        const formattedData = responseData.map(function (definition) {
          return {
            shortDefinitions: definition.shortdef,
            partOfSpeech: definition.fl,
            word: definition.hwi.hw,
            uuid: definition.meta.uuid,
          };
        });
        this.wordDefinitions = formattedData;
      } catch (error) {
        console.error(error);
      }
    },
    resetSearch() {
      this.typedWord = "";
      this.wordDefinitions = [];
    },
  },
};
</script>
<style scoped>
.definition {
  border: 1px solid black;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}
</style>
