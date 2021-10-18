<template>
  <div>
    <label for="word">{{ message }}</label>

    <input type="search" id="word" name="word" />
    <button>search</button>
  </div>
</template>

<script>
export default {
  name: "WordInput",
  data() {
    return {
      typedWord: "abc",
      message: "Type your word here",
    };
  },
};
</script>
