<template>
  <div class="home">
    <Survey class="surveyPage"></Survey>
    <Result class="resultPage"></Result>
  </div>
</template>

<script>
import content from "../components/content.vue";
import sidebar from "../components/sidebar.vue";
export default {
  name: "home",
  components: {
    Survey: content,
    Result: sidebar
  }
};
</script>
<style scoped>
.home {
  display: flex;
}
.surveyPage {
  background-color: rgb(230, 230, 230);
  width: 75%;
}
.resultPage {
  position: fixed;
  background-color: rgb(255, 255, 255);
  width: 25%;
  height: 100vh;
  margin-left: 75%;
}
</style>
