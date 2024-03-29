# 기본 요청 사항
## Router
- [x] 링크 공유 페이지 url path는 ‘/shared’가 되도록 만들어 주세요.
- [x] 폴더 페이지의 url path는 ‘/folder’가 되도록 설정해 주세요.
## ui
- [x] 폴더 페이지에 저장된 링크가 없는 경우 해당(저장된 링크가 없습니다) 디자인이 보이도록 만들어 주세요.
- [x] 폴더 페이지에서 상단 네비게이션 바는 스크롤 시 상단에 고정하지 않고, 가려지도록 해주세요.
- [x] 링크 추가하기, 폴더 추가, 공유, 이름 변경, 삭제 버튼들의 기능은 추후 만듭니다.
- [x] “전체” 폴더를 선택한 경우 “공유”, “이름 변경”, “삭제” 버튼들이 보이지 않지만, 다른 폴더를 선택한 경우에는 버튼들이 보이도록 해주세요.
- [x] Mobile에서 “폴더 추가" 버튼은 최하단에서 101px 떨어져있는 Button으로 만들어 주세요. (floating action Button이란?)
## api
- [x] 폴더 목록에 필요한 데이터는 “/api/users/1/folders”를 활용해 주세요.
- [x] “전체” 폴더에 필요한 링크들 데이터는 “/api/users/1/links”를 활용하고, 이외의 폴더에 필요한 링크들 데이터는 “/api/users/1/links?folderId={해당 폴더 ID}”를 활용해 주세요.
- [x] 폴더 버튼을 클릭하면 폴더에 해당하는 링크들로 카드를 구성해 주세요. 폴더에 링크 데이터가 없을 때는 저장된 링크가 없다는 UI를 보여주세요.
- [x] 프로필 영역의 데이터는 https://bootcamp-api.codeit.kr/docs 에 명세된 “/api/users/1”을 활용해 주세요.
## 컴포넌트
- [x] 카드 컴포넌트에 별모양 버튼, 케밥 버튼도 추가해 주세요.


# 추가 사항 정리 (지난주 피드백 반영)
## 컴포넌트
- [x] 컴포넌트 내부에서 관리하는 자원과 외부(부모 요소)에서 관리하는 자원을 구별한다.
  - [x] 레이아웃과 관련된 것은 컴포넌트 외부에서 관리한다.
- [x] className을 props로 넘겨줄 지, 해당 컴포넌트를 호출하는 부모 요소에서 div로 처리할 지 분명히 구별한다.

## React
- [x] 컴포넌트의 지나친 재사용성, 추상화를 경계한다. (css 선택자 관련)
- [x] StrictMode 컴포넌트는 지우지 않는다.
### 훅 관련
- [x] state 훅 사용을 최소화한다. (관리하는 상태가 많아지는 것은 좋지 않다.)
- [x] useEffect 훅은 하나의 동작만을 이행하는 것이 좋다.
- [x] 커스텀 훅을 만드는 기준을 세우고, 관리한다.
### jsx(html 태그) 관련
- [x] a 태그에서 rel 속성에 noopener도 추가한다.
- [x] 컴포넌트 내부 jsx 에서도 시맨틱 태그를 적극 사용한다.
- [x] alt 속성에는 "이미지"라는 단어는 지양한다.
### 배열 관련
- [x] key 값은 배열 내에서 유일해야 한다.
- [x] Frame(현재는Folder)의 카드 컴포넌트 props를 구조 분해 할당한다.
- [x] 배열을 사용할 수 있는 jsx를 잘 판단한다.
- [x] 카드 컴포넌트 배열 요소를 li, ul로 적용해본다.
### 컨벤션 관련
- [x] 컴포넌트 네이밍을 선언적으로 한다.
- [x] 컴포넌트 파일명 확장자는 jsx다.
### 렌더링
- [x] 조건부 렌더링의 다양한 방법을 상황에 맞게 적용한다.
- [x] 상수는 컴포넌트 외부에서 관리한다.

## 함수, 메서드
- [x] 절차가 단순한 코드를 함수화하는 것은 지양한다.
- [x] 한 함수가 한 가지 기능만 담당하게 한다.
  - [x] 함수가 한 가지 기능을 하는지 확인하는 기준을 세운다.
  - [x] 특히, 함수 역할의 일관성을 고민한다.
- [x] 함수형 프로그래밍을 고민해본다. 함수가 외부 변수에 의해 동작하지 않는지 점검한다.
  - [x] 특히, 전역 변수에 의존하는 이벤트를 점검한다. 이를 지역 변수와 인자로 처리한다.
  - [x] 함수의 인자를 최소화한다.
### 네이밍 관련
- [x] 함수의 이름과 역할을 분명히 한다.
### 컨벤션 관련
- [x] indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다. 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다. 
  - [x] 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- [x] 함수(또는 메서드)의 길이가 15라인을 넘어가지 않도록 구현한다.
- [x] else를 지양한다.
    - [x] 힌트: if 조건절에서 값을 return하는 방식으로 구현하면 else를 사용하지 않아도 된다.
    - [x] 때로는 if/else, switch문을 사용하는 것이 더 깔끔해 보일 수 있다. 어느 경우에 쓰는 것이 적절할지 스스로 고민해 본다.
- [ ] 값을 하드 코딩하지 않는다.

## js
- [x] 자바스크립트 api를 적극 활용한다.
- [x] let과 const 사용 기준을 명확히 한다.
- [x] js를 통해 css 스타일링 적용 시, 불필요하게 명시도가 높아지는 것을 유의한다.
- [x] 함수는 객체다. 즉, 함수를 선언하고 반드시 새로운 변수에 할당할 필요는 없다.
- [x] 구조 분해 할당과 map 배열을 적극적으로 이용한다.
- [x] 3항 연산자를 적절히 활용한다. 특히, 조건부 렌더링에서 유용하다.

## css
- [x] 디자인 사항을 번경하지 않는다.
### 컨벤션 관련
- [x] 전역에 선언할 Css 속성을 고민한다.
- [x] css 미디어 쿼리도 컨벤션을 적용힌다.
- [x] reset.css를 활용한다. (사용자 에이전트 스타일시트의 사이드 이펙트를 차단한다.)
  - [x] reset.css는 전역 속성으로 정의하는 속성도 활용할 수 있다.
### 네이밍 관련
- [ ] css 네이밍에 대해 다시 고민해본다.

## 코드 컨벤션
- [x] 이름을 통해, 의도를 드러낸다. (https://jacking75.github.io/ETC_good_function_name/ 참고)
- [x] 축약하지 않는다.
- [x] 공백도 코딩 컨벤션이다.
- [x] 공백 라인 의미있게 사용한다.
- [x] 스페이스와 탭을 혼용하지 않는다.
- [x] 의미 없는 주석을 달지 않는다.
- [x] 불필요한 console.log를 남기지 않는다.
- [x] 파일 이름(단 컴포넌트 파일은 제외)은 카멜 케이스를 적용한다.
- [x] Prettier를 활용한다. 
  - [x] 코드 포멧팅에 유의한다.
- [x] import React from 'react';는 17 버전 이후로 사용하지 않는다.
### 상수 관련
- [x] 상수의 기준을 명확히 한다.
  - [x] 상수의 네이밍은 대문자 스네이크 케이스다.
  - [x] 상수는 외부에서 호출해야 마땅하다.
### 네이밍 관련
- [x] 네이밍에는 자료형에 대한 정보도 담아야 한다.
- [x] 이미지(assets의 png, svg)에 대한 네이밍도 신경 쓴다.
- [x] import 코드 컨벤션도 적용한다.
  - builtin (node.js 자체에 내장된 모듈)
  - external (다운로드 받은 라이브러리)
  - internal (프로젝트 내부에 직접 작성한 모듈)
  - 계층별로 구분 (상수, 컴포넌트, 유틸등)

## api 비동기 처리
- [ ] 서버로 보낸 요청에 대해 성공했는지 response.ok와 같은 값으로 확인해주는 과정이 필요하다.

# 자체 피드백
## css
- [ ] 별표 버튼이 배경 위에 오는 것 -> position 방식 말고는 없는가.
- [ ] 그리드에 대한 공부 필요
- [ ] css 리팩토링 해보기 (style components)

## 계층(아키텍쳐)
- [x] 커스텀 훅을 통해, api 계층과 컴포넌트의 결합도를 낮춘다.
- [ ] 페이지 전환에 대해 고민한다.
 - [ ] link, navlink를 적용하는 방법
 - [ ] uselocation 활용 방법은?
 - [ ] 현재 index 페이지가 없다. -> 회원 가입 기능과의 연동 고려
 - [ ] 폴더 목록을 페이지 전환해야 하는지 고민한다.

## 컴포넌트
- [x] 컴포넌트를 나누는 기준을 세운다.
 - [x] 특히 하나의 컴포넌트에 너무 많은 조건부 렌더링은 지양한다.
 - [x] 폴더 컴포넌트를 리팩토링한다.

 # 멘토님 피드백
 ## 설정
 - [x] 파일명을 대문자, 소문자 변경 시, git Config에 유의한다.
 - [x] eslint는 eslint만 설치해서 사용하기보다는 plugin, config가 붙은 패키지들을 설치해 규칙을 만든다.
 - [x] dependencies 패키지와 devDependencies 패키지를 구별한다.
 - [x] 패키지 버전 앞에 붙어있는 ^(캐럿)에 대해서도 고려한다.