<template>
  <div class="survey">
    <div class="qBox" id="question1">
      <h2>당신은 하루에 몇 시간 정도 잠을 잡니까?</h2>
      <div class="ansBox">
        <button class="Btn shadow" value="4시간 미만" @click="answer">4시간 미만</button>
        <button class="Btn shadow" value="4시간 이상" @click="answer">4시간 이상</button>
        <button class="Btn shadow" value="5시간 이상" @click="answer">5시간 이상</button>
        <button class="Btn shadow" value="6시간 이상" @click="answer">6시간 이상</button>
        <button class="Btn shadow" value="8시간 이상" @click="answer">8시간 이상</button>
      </div>
      <scrollactive
        :offset="10"
        :duration="600"
        :modifyUrl="false"
        bezier-easing-value=".5,0,.35,1"
        v-on:itemchanged="onItemChanged"
      >
        <a href="#question2" class="scrollactive-item nextBtn shadow" @click="submit1">다음</a>
      </scrollactive>
    </div>
    <div class="qBox" id="question2">
      <h2>당신은 하루에 몇 끼의 식사를 합니까?</h2>
      <div class="ansBox">
        <button class="Btn shadow" value="한 끼" @click="answer">한 끼</button>
        <button class="Btn shadow" value="두 끼" @click="answer">두 끼</button>
        <button class="Btn shadow" value="세 끼" @click="answer">세 끼</button>
        <button class="Btn shadow" value="세 끼 이상" @click="answer">세 끼 이상</button>
      </div>
      <scrollactive
        :offset="10"
        :duration="600"
        :modifyUrl="false"
        bezier-easing-value=".5,0,.35,1"
        v-on:itemchanged="onItemChanged"
      >
        <a href="#question3" class="scrollactive-item nextBtn shadow" @click="submit2">다음</a>
      </scrollactive>
    </div>
    <div class="qBox" id="question3">
      <h2>당신은 일년간 몇 권의 책을 읽습니까?</h2>
      <div class="ansBox">
        <button class="Btn shadow" value="1권 미만" @click="answer">1권 미만</button>
        <button class="Btn shadow" value="5권 미만" @click="answer">5권 미만</button>
        <button class="Btn shadow" value="10권 미만" @click="answer">10권 미만</button>
        <button class="Btn shadow" value="20권 미만" @click="answer">20권 미만</button>
        <button class="Btn shadow" value="20권 이상" @click="answer">20권 이상</button>
      </div>
      <a href="#footer" class="scrollactive-item nextBtn shadow" @click="submit3">다음</a>
    </div>

    <div class="footer" id="footer">
      <scrollactive
        :offset="10"
        :duration="600"
        :modifyUrl="false"
        bezier-easing-value=".5,0,.35,1"
        v-on:itemchanged="onItemChanged"
      >
        <a href="#question1" class="scrollactive-item endBtn" @click="end">설문완료</a>
      </scrollactive>
    </div>
  </div>
</template>

<script>
export default {
  name: "survey",
  data() {
    return {
      ans: ""
    };
  },
  methods: {
    onItemChanged() {},
    submit1() {
      localStorage.setItem(0, this.ans);
    },
    submit2() {
      localStorage.setItem(1, this.ans);
    },
    submit3() {
      localStorage.setItem(2, this.ans);
    },
    // 다음 버튼을 눌렀을 때 질문 페이지 하나당 로컬스토리지 키 하나를 할당하여, ans 값을 저장
    answer(event) {
      var a = event.target.value;
      this.ans = a;
    },
    //선택지(버튼)를 눌렀을때 event 해당 선택지의 값(event.target.value)을 ans에 임시 저장.
    end() {
      localStorage.clear();
    }
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
.endBtn {
  text-align: center;
  display: inline-block;
  background: transparent;
  width: 200px;
  height: 50px;
  padding-top: 2rem;
  color: black;
}
</style>
