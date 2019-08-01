<template>
  <div class="home">
    <Survey class="surveyPage" v-on:submit="submit" v-on:clearAll="clearAll"></Survey>
    <Result class="resultPage" v-bind:propsdata="answerArray"></Result>
  </div>
</template>

<script>
import content from "../components/content.vue";
import sidebar from "../components/sidebar.vue";
export default {
  name: "home",
  data() {
    return {
      answerArray: new Array()
    };
  },
  components: {
    Survey: content,
    Result: sidebar
  },
  methods: {
    submit(answers) {
      this.answerArray = answers;
    },
    clearAll() {
      this.answerArray = [];
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
span {
  font-weight: bold;
}
.results {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  margin-top: 70%;

  font-size: 1.2em;
  font-weight: 300;
}
</style>
