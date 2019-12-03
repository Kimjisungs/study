## DATA TYPES

1. 기본형 : number, string, boolean, null, nudefined
2. 참조형 : 객체 -> array, function, regExp



## 실행 컨텍스트 (실행 맥락/환경/상황)

실행에 필요한 코드 흐름상의 배경이 되는 상황과 조건. 코드 뭉치. 실행할때 필요한 조건, 환경 정보,

ex) es5) 함수, 전역공간 -> 전역 컨텍스트, 지역 컨텍스트

함수를 실행할 때 필요한 환경정보. 

환경정보를 담은 객체 스택.

실행을 하는것, 콜 스택,

어떤 함수가 동작하고 있는지, 다음에 어떤 함수가 호출하는지 실행 동작원리. 

 

Lexicl Environment

어휘적, 사전적 환경 



Hosting - 실행 컨텍스트 최 상위로 끌어올린다.  끌어올라가있는 내용 전체가

environmentRecord이다. 



outerEnvironmentReference 외부 환경에 의한 참조. 현재 문맥에 관련 있는 외부 식별자 정보. 

outerEnvironmentReference가 관여하는것이 스코프 체인이다. 

scope는 변수의 유효 범위이다. 실행 컨텍스트에 의해서 만들어 진다. 

scope chain도 실행컨텍스트에 의해 결정이 된다.

scope는 밖으로갈 수있는데 안쪽으로 갈 수 없다. laxical environment때문에 

inner에 enviromentRecord를 찾고, outer을 찾고전역을 찾고 , lexicalenvironment에 의해

실행컨텍스트는 환경정보를 담은 객체 

environmentrRecord : 현재 문맥의 식별자

outerEnvironmentReference 외부 식별자

