<template>
  <div class="footer" id="footer">
    <a href="#question1" class="scrollactive-item endBtn" @click="end">설문완료</a>
  </div>
</template>

<script>
export default {
  name: "contentfooter",
  //선택지(버튼)를 눌렀을때 event 해당 선택지의 값(event.target.value)을 ans에 임시 저장.
  methods: {
    end() {
      this.$emit("clearAll");
    }
  }

  // 설문완료 누르면 로컬스토리지 비움!
};
</script>

<style>
.endBtn {
  text-align: center;
  display: inline-block;
  background: transparent;
  width: 200px;
  height: 50px;
  padding-top: 2rem;
  color: black;
}
a {
  text-decoration: none;
}
</style>
