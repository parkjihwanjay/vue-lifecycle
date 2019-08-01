<template>
  <div class="qBox" id="question3">
    <h2>당신은 일년간 몇 권의 책을 읽습니까?</h2>
    <div class="ansBox">
      <button class="Btn shadow" value="1권 미만" @click="answer">1권 미만</button>
      <button class="Btn shadow" value="5권 미만" @click="answer">5권 미만</button>
      <button class="Btn shadow" value="10권 미만" @click="answer">10권 미만</button>
      <button class="Btn shadow" value="20권 미만" @click="answer">20권 미만</button>
      <button class="Btn shadow" value="20권 이상" @click="answer">20권 이상</button>
    </div>
    <a href="#footer" class="scrollactive-item nextBtn shadow" @click="submit">다음</a>
  </div>
</template>

<script>
export default {
  name: "content3",
  data() {
    return {
      ans: "",
      index: 2
    };
  },
  methods: {
    submit() {
      this.$emit("submit", this.index, this.ans);
    },

    answer(event) {
      var a = event.target.value;
      this.ans = a;
    }
  }
};
</script>

<style scoped>
.qBox {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: rgb(255, 255, 255);
  height: 100vh;
  margin: auto;
}
.ansBox {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 40%;
  height: 50%;
  margin-top: 8%;
}
.Btn {
  text-align: center;
  display: inline-block;
  background: transparent;
  border-radius: 5px;
  border: none;
  width: 14rem;
  height: 6rem;
  margin: 4px 2px;
  transition-duration: 0.4s;
  color: rgb(77, 77, 77);
  font-family: "나눔바른고딕";
  font-weight: 300;
  font-size: 1.1rem;
}
.Btn:hover {
  background: linear-gradient(to right, #ce9ffc, #7367f0);
  color: rgb(255, 255, 255);
}
.Btn:focus {
  outline: none;
  background: linear-gradient(to right, #ce9ffc, #7367f0);
  color: rgb(255, 255, 255);
}
a {
  text-decoration: none;
}
.nextBtn {
  outline-color: #f76b1c;
  text-align: center;
  display: inline-block;
  background: transparent;
  border: 1px solid #f76b1c;
  border-radius: 5px;
  width: 48px;
  height: 24px;
  padding: 16px 32px;
  margin-left: 700px;
  transition-duration: 0.4s;
  color: rgb(77, 77, 77);
  font-weight: 300;
  font-size: 1.1rem;
}
.nextBtn:hover {
  background: linear-gradient(to top, #fad961, #f76b1c);
  color: rgb(255, 255, 255);
}
</style>