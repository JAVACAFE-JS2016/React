# Why React?

  - 참고자료
  [FBDG 2015 Nov - Facebook은 React를 왜 만들었는가?](https://www.youtube.com/watch?v=iAJCdfgYQtw "youtube")

  1. 배경
    - backbone.js, underscore.js 등등 -> 웹프론트엔트 환경에 맞게 MVC 재해석, 도메인 모델+REST API
      - 문제점 : 동기화 잘안됨.  
    - 데이터 바인딩 : View-Model 동기화 => ember.js
    - Angular.js : 양방향 데이터 바인딩, POJO + Dirty Checking
      - 데이터량이나 컴포넌트 많을떄 성능이슈 있음(모바일), 학습비용이 큼
    - React 관심사 : 컴포넌트 사용(재사용을 위해서)

  2. Why React?
    - React는 사용자 인터페이스를 위한 Javascript 라이브러리(프레임워크 아님)(MVC에서 V 담당)
    - 참고)
        - AngularJS => 프레임워크
        - React => Only View (Ajax, Router 등이 없음, 가벼움)
    - 큰 어플리케이션에서 데이터 변화를 해결하기 위해서 만들어짐

  3. 특징
    - 컴포넌트 기반 아키텍쳐
        - React.Component 클래스를 상속한 자바스크립트 컴포넌트
        ~~~
          class StoryBox extends React.Component{
            render(){ //모든 컴포넌트는 render() 필요
              return(
                <div>Story box</div>
              )
            }
          }
        ~~~
    - Virtual DOM
        - 실제 DOM 객체의 in-memory representation
        - 페이지가 바뀌기전 컴포넌트 생성
        ~~~
        <!--output 1>
        <div>
          <p>Good morning</p>
          <p>10:00</p>
        </div>

        <!--output 2>
        <div>
          <p>Good morning</p>
          <p>10:05</p>
        </div>
        ~~~
        
  4. 싱글 페이지 어플리케이션 생성
  ~~~~
  npm install create-react-app
  create-react-app hello-world
  cd hello-world
  npm start
  ~~~~

  5. React DOM
   - 클라이언트 패키지 관리 하고 싶을 때 React-dom 추가 (DOM 랜더링 역할)
   - 단, Babel 설치가 되어 있어야함. (ES5 변환)
    ~~~
    npm install --save react react-dom
    ~~~

    - 예시)
    ~~~
    import React from 'react';  //컴포넌트 담당
    import ReactDOM from 'react-dom'; //DOM 랜더링 역할

    ReactDOM.render(
      <h1>Hello, world!</h1>,
      document.getElementById('root')
    );
    ~~~
    
  
   6. ES6와 JSX 호환
    - React는 Babel과 함께 사용하는 것을 권장 (참고:IE8 이하 지원하지 않음!!)
    - babel-preset-react와 babel-preset-es2015 설치하고, .babelrc 에 가능하게 해야함.

   7. CDN 사용
      - npm 사용하고 싶지 않은 경우, CDN으로 사용. dis 폴더 하위에 있는 js 파일 사용하면 됨
      ~~~
      <script src="https://unpkg.com/react@15/dist/react.min.js"></script>
      <script src="https://unpkg.com/react-dom@15/dist/react-dom.min.js"></script>
      ~~~

  8. Virtual DOM
    - 실제 DOM 처리하는 것은 비효율적
    - DOM을 추상화, 자바스크립트의 추상화

  9. React Application 의 흐름 예
    - index.html -> static HTML 파일 로드
    - something.js -> React 라이브러리와 사용자 컴포넌트가 로드됨
    - ReactDom 이 컴포넌트로 랜더링됨
    - Virtual DOM 이 실제 DOM으로 바뀜
    
# react test site
https://codepen.io/pen/
- 여기에서 Babel 설정(ES6 이전 문법으로 전환)
- Quick-add에서 React(컴포넌트 담당), React DOM(DOM 랜더링) 선택

# 리액트 요약
  - React was built to solve one problem:building large applications with data that changes over time
  - In React, we write apps in terms of components.
  - We use JavaScript classes when declaring React components.
  - Components must extend the React.Component class and must contain a render() method.
  - We call the ReactDOM.render() function to render components to a web page.
