# survey 연습

## Project setup ! 
```
git clone으로 파일을 내려받으신 후에

$npm install
$npm run serve
```

## 파일 구조 설명
```
-현재 디렉토리 구성은 아래와 같습니다.

  src
  |-components
  |--content.vue
  |--sidebar.vue
  |-plugin
  |-views
  |--About.vue
  |--Home.vue
  |-App.vue각
  
지난 강의와 마찬가지로 App.vue 에서 작업하셔도 상관 없지만, 
일단 기본값으로 views/Home.vue 에 컴포넌트 두개를 불러왔습니다.
따라서 현재는 Home.vue가 통합 컴포넌트인 상태입니다! 
여기서 작업하셔도 되고, App.vue 최상위 컴포넌트에서 작업하고 싶으신 분들은
Home.vue에서 컴포넌트를 삭제한 뒤 App.vue에 컴포넌트를 새로 등록하셔서 시작하시면 됩니다. 
```
## 기능설명
```
content.vue method에 간략하게 설명이 되어있습니다. 
  1. '선택지(버튼)'를 클릭하고
  2. '다음' 버튼을 클릭하면 화면이 넘어가면서 
      로컬 스토리지에 해당 선택지가 저장됩니다. (개발자도구 Application에서 확인)
  3.  3번 설문까지 작성후 새로고침을 하시면 
      화면 오른쪽에 sidebar 가 출력되는 것을 확인할 수 있습니다!
  4.  설문완료를 누르면 로컬 스토리지가 비워지고 1번 설문으로 돌아갑니다.
```

