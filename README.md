# learn-nuxt

## 할 일

- [ ] 메인 페이지의 검색 박스, 리스트 아이템 컴포넌트화
- [ ] 검색 박스에서 검색할 때 debounce 걸어주기
- [ ] 메인, 상세 페이지의 헤더를 레이아웃 컴포넌트에서 선언해주기

## 수업 과정 흐름 정리

메인 페이지와 상세 페이지의 기능을 어느 정도 구현 후 설계한 교과과정 보고 프로젝트 생성부터 자잘한 기능들 어떤 순서로 가져갈지 정리해 보기

## 수업 순서

- nuxt 프로젝트 생성 및 실행 확ㅇ인
- 페이지 컴포넌트 제작
  - 상세 페이지 컴포넌트 `detail.vue` 생성 후 `h1` 태그 정도로 페이지 이름 정도만 텍스트로 기입
  - [ ] 잘못된 URL로 접근했을 때의 에러 페이지 접근 방법 및 스타일링 방법 안내
- 레이아웃 개념 안내
  - `default.vue` 레이아웃에서 공통 레이아웃 요소인 헤더 컴포넌트 등록 및 `NuxtLink`로 페이지 클릭 이동 방법 안내
- 백엔드 API 안내
  - `backend`에서 노드 모듈 설치 후 실행 방법 안내 후 서버 실행하여 `localhost:3000` API 확인
- 스타일 시트 안내
  - `assets/css`에 위치
- 메인 페이지 제작
  - 데이터 표시해서 화면에 뿌려주기
  - 검색 박스, 리스트 아이템 컴포넌트화
- 상세 페이지 연결
  - 메인 페이지의 상품 정보 클릭했을 때 상세 페이지로 연결되도록 넉스트의 다이나믹 페이지 라우팅 방법 안내
- 상세 페이지 제작
  - asyncData, fetch를 이용한 상세 페이지 정보 호출 
