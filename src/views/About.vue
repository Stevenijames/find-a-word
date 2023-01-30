<template>
  <div class="about">
    <h2>Welcome to Find A Word!</h2>
    <p>
      This is a dictionary app uses the free Merrian Webster Dictionary API.
      This API give comprehensive and dictionary and thesaurus conent.
    </p>
    <p>
      This free API is limited to 1000 non-commercial queries per day per API
      Key. Limited to two reference APIs.
    </p>
  </div>
  <p>Simply click the button to begin</p>
</template>

<script>
export default {
  name: "About",
};
</script>

<style scoped>
.about {
  display: flex;
  border: 2px solid #d3d3d3;
}
</style>
