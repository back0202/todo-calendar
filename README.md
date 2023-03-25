# ui
- Calendar
  - Header
    - ArrowButton
    - Title
    - ArrowButton
  - Table
    - TableHeader
      - tr
        - th
    - TableBody
      - tr
        - td
          - DisplayDate
          - TodoList
            - TodoItem
            - EtcItem
- TodoFormModal
  - modal
    - Portal
      - Overlay
        - Dim
        - Card
          - Date
          - InputTodo
- TodoStatisticsModal
  - modal
    - Portal
      - Overlay
        - Dim
        - Card
          - Date
          - Statistics
          - TodoList
            - TodoItem
               - Content
               - TodoActions
                - TodoActionButton
# 로직
## Calendar
- 달력번호 클릭시 selectedDateState변경
- 달력번호 더블클릭시 TodoStatisticsModalOpen을 true로 변경, selectedDateState변경
- td 더블클릭시 TodoFormModalOpen을 true로 변경, selectedDateState변경
- todo 클릭시 selectedTodo 변경
- 전체 todo 클릭시 TodoStatisticsModalOpen true로 변경
## TodoFormModal
- input 엔터시 todoList추가, input포커스와 input value삭제, TodoFormModal false로 변경 
## TodoStatisticsModal
- 제거 클릭시 todoList

# 고민한거
1. 모달을 왜 Calendar과 같은 위치에 두나
- Portal을 사용하면 최상단에 modal이 나올텐데 저 위치에 있을 필요가 있을까 고민. modal은 calendar위에 띄우는거니 레이아웃? 구조상 저 위치가 맞지 않을까
2. 구현 할때 순서
- 최상위 레이아웃 부터 생각하며 ui 그리기
- 최하위 요소 부터 로직 생각하기
- 최상위 요소부터 로직 
# 알게된거
## 컴포넌트 추상화
1. https://fe-developers.kakaoent.com/2022/221020-component-abstraction/
2. https://fe-developers.kakaoent.com/2022/220731-composition-component/
3. https://ko.reactjs.org/docs/composition-vs-inheritance.html

- 몇달동안 고민 했었는데 이제 알거 같다. 
- 아이폰11 과 아이폰 12가 있다면, 공통된 코드가 반복이 될것이다. 객체지향에서는 아이폰이라는 것으로 추상화를 해서 아이폰을 상속받아서 아이폰11과 아이폰12를 만든다. 컴포넌트는 어떻게 이런 추상화를 해야하는가에 대한 고민을 몇달 동안 했었는데 이제야 조금 알거 같다. 공통으로 사용하는 modal로 추상화하고 modal을 사용하는 TodoFormModal이나 TodoStatisticsModal에서 modal에 자식으로 넣어주면 되는거 같다.
## recoil
https://velog.io/@toyo8/recoil-%EC%9D%B4%EB%9E%80
## 더블클릭 이벤트
## 키다운 백스페이스
## 배열에 컴포넌트 넣기

