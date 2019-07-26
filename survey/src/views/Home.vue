<template>
  <div class="home">
    <Survey class="surveyPage" v-on:submit="submit" v-on:clearAll="clearAll"></Survey>
    <Result class="resultPage" v-bind:propsdata="answers"></Result>
  </div>
</template>

<script>
import content from "../components/content.vue";
import sidebar from "../components/sidebar.vue";
export default {
  name: "home",
  data() {
    return {
      answers: []
    };
  },
  components: {
    Survey: content,
    Result: sidebar
  },
  methods: {
    submit(index, ans) {
      localStorage.setItem(index, ans);
      this.answers.push(ans);
    },
    clearAll() {
      localStorage.clear();
      this.answers = [];
    }
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
