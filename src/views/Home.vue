<template>
  <div class="home">
    <img
      alt="Vue logo"
      src="../assets/find-a-word-logo-white.png"
      class="logo"
    />
    <h3>Search for a word and see it dynamically displayed</h3>
    <WordInput />
    <!-- <CountIncDec /> -->
  </div>
</template>

<script>
// @ is an alias to /src
import WordInput from "@/components/WordInput.vue";
// import CountIncDec from "@/components/CountIncDec.vue";

export default {
  name: "Home",
  components: {
    WordInput,
    // CountIncDec,
  },
};
</script>

<style scoped>
.logo {
  width: auto;
  height: auto;
}
</style>
