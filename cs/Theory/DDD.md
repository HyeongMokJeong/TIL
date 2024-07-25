- Aggregate에 대한 기준
1. 함께 생성되고 함께 삭제되는 객체들을 함께 묶어라
   -> 연관 객체들의 생명주기를 루트 도메인에서 관리
2. 도메인 제약사항을 공유하는 객체들을 함께 묶어라
3. 가능하면 분리하라

- 하나의 Aggregate에 하나의 Repository
1. 실질적으로 직접 접근해야 하는 AGGREGATE의 루트에 대해서만 REPOSITORY를 제공하고, 
   모든 객체 저장과 접근은 REPOSITORY에 위임해서 클라이언트가 모델에 집중하게 하라.
2. 하나의 Aggregate에 여러 Repository가 존재한다면?
   -> 정말 같은 Aggregate인지