<template>
  <div class="qBox" id="question2">
    <h2>당신은 하루에 몇 끼의 식사를 합니까?</h2>
    <div class="ansBox">
      <button class="Btn shadow" value="한 끼" @click="answer">한 끼</button>
      <button class="Btn shadow" value="두 끼" @click="answer">두 끼</button>
      <button class="Btn shadow" value="세 끼" @click="answer">세 끼</button>
      <button class="Btn shadow" value="세 끼 이상" @click="answer">세 끼 이상</button>
    </div>

    <a href="#question3" class="scrollactive-item nextBtn shadow" @click="submit">다음</a>
  </div>
</template>

<script>
export default {
  name: "content2",
  data() {
    return {
      ans: "",
      index: 1
    };
  },
  methods: {
    submit() {
      //   localStorage.setItem(this.index, this.ans);
      this.$emit("submit", this.index, this.ans);
    },
    // 다음 버튼을 눌렀을 때 질문 페이지 하나당 로컬스토리지 키 하나를 할당하여, ans 값을 저장
    answer(event) {
      var a = event.target.value;
      this.ans = a;
    },
    //선택지(버튼)를 눌렀을때 event 해당 선택지의 값(event.target.value)을 ans에 임시 저장.

    // 설문완료 누르면 로컬스토리지 비움!
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