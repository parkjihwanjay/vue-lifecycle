<template>
  <div class="survey">
    <content1 v-on:submit="submit"></content1>
    <content2 v-on:submit="submit"></content2>
    <content3 v-on:submit="submit"></content3>
    <contentfooter v-on:clearAll="clearAll"></contentfooter>
  </div>
</template>

<script>
import content1 from "./content1.vue";
import content2 from "./content2.vue";
import content3 from "./content3.vue";
import contentfooter from "./contentfooter.vue";
export default {
  name: "survey",

  data() {
    return {
      answers: new Array()
    };
  },

  components: {
    content1: content1,
    content2: content2,
    content3: content3,
    contentfooter: contentfooter
  },

  methods: {
    submit(index, ans) {
      this.answers[index] = ans;
      localStorage.setItem(index, ans);
      this.$emit("submit", this.answers);
    },
    clearAll() {
      localStorage.clear();
      this.answers = [];
      this.$emit("clearAll");
    }
  }
};
</script>

<style scoped>
</style>

