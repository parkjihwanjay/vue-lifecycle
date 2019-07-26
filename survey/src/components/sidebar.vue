<template >
  <div class="sidebar">
    <div class="results">
      <p v-if="this.answers[0]">
        저는 하루에
        <span>{{ answers[0] }}</span> 잠을 잡니다.
      </p>
      <p v-if="this.answers[1]">
        저는 하루에
        <span>{{ answers[1] }}</span>의 식사를 합니다.
      </p>
      <p v-if="this.answers[2]">
        저는 일년에
        <span>{{ answers[2] }}</span>의 책을 읽습니다.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "sidebar",
  data() {
    return {
      answers: []
    };
  },
  created() {
    if (localStorage.length > 0) {
      for (var i = 0; i < localStorage.length; i++) {
        this.answers.push(localStorage.getItem(i));
      }
    }
  }
  // 로컬스토리지에서 getItem()을 이용하여 0~2 index의 value를 받아오는 매서드
};
</script>

<style scoped>
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