# Vue

## Vue 왜 쓸까?

Web-app만들때 쓴다.

React, Angular, Vue 그런데 왜 Vue를 쓸 까?

1. 쉬어서 사용한다. 무엇이 쉬울까? 다 똑같은 결과물을 만들어내는데, 문법이 다르다.
2. 코드를 짤 때 방법이 있다.
   - React는 map, forEach 등 쓸 수 있다.
   - Vue는 v-for을 사용한다. 이런 차이점, v-if, v-else로 조건문을 나타낸다
3. HTML 렌더링이 리액트보다 빠르다. (ms차이…)
4. 업데이트 잘 됨

App.vue를 HTML로 컴파일 후 index.html로 바뀐 후 렌더링 된다.

## 문법

{{ 데이터 바인딩 }} 하는이유

1. HTML에 하드코딩 해놓으면 나중에 변경이 어려움
2. 실시간 자동 렌더링을 하려면 데이터 바인딩 문법으로 해야한다.

- 데이터 변경되면, 자동으로 HTML에도 실시간으로 반영됨. 즉, 실시간 자동 렌더링이 된다.
- 그로 인해서, 웹, 앱을 만들 수 있다.
- 자주 변경이 안되는 부분은 데이터 바인딩을 안하는게 좋다. 애초에 바뀔일이 없다면 자동 렌더링 하지 않게 하는것이 효율적이다.

HTML 속성 데이터 바인딩은
:속성 = "데이터이름" (문법이 그렇다.)

## 반복문

      <a v-for="tag in 3" :key="tag">Home</a>

      v-for"작명 in 몇 번 반복시킬 것인가" :key="작명"

만약 배열상태로 반복문을 돌리고 싶다면
data() {
return {
menu: ['Home', 'Shop', 'About'],
};
},

      <a v-for="tag in menu" :key="tag">{{ tag }}</a>

1. menu의 크기 만큼 반복시킨다.
2. 그 해당하는 작명한 변수는 데이터 안의 자료가 된다.

key를 쓰는 이유는

- 반복문 쓸 때 꼭 써야한다.
- 반복문 돌린 요소를 구분하기 위해 쓴다. 그래서 유니크한 숫자/문자를 넣어야한다.

      <a v-for="(tag, i) in menu" :key="i">{{ tag }}</a>

## 함수

data가 끝나는 부근에 methods: {} 입력 후 그 안에 함수를 생성.

    <button @click="increase">허위매물신고</button>

methods: {
increase() {
this.count += 1;
},
},

## 조건문

      <div class="black-bg" v-if="modalState">

      modalState: false,
      //조건문 v-if로 이뤄진다.

      <div v-else>두번째거</div>
      //위 조건문 if가 거짓이라면 else문이 동작

## 컴포넌트

자식 컴포넌트의 만들어도 되는데, 부모도 쓰는 데이터라면 부모컴포넌트에
만들어두는게 좋다.
