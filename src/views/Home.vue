<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <WordInput />
    <CountIncDec />
  </div>
</template>

<script>
// @ is an alias to /src
import WordInput from "@/components/WordInput.vue";
import CountIncDec from "@/components/CountIncDec.vue";

export default {
  name: "Home",
  components: {
    WordInput,
    CountIncDec,
  },
};
</script>
