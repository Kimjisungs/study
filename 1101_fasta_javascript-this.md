## THIS

함수의 호출  방식에 따라 다르다.

ThisBinding This가 달라진다

1. 전역공간에서  :  window / global
2. 함수 호출시 : window / global  
3. 메소드 호출시 : 메소드 호출 주체, 메소드 앞에 점 앞에
4. callback 호출시 : 기본적으로 함수 내부에 대해서 동작, 지정하는 혹은 어떻게 처리하는 것이냐에 따라 달라진다. 
5. 생성자 함수 호출시 : 인스턴스

우회법 var self = this, bind(this)

 call, apply, bind : this를 지정할 수 있다. 

콜백함수의 this는 지정하는 것에 따라 달라진다. 

### 정리

- 기본적으로 함수의 this와 같다.
- 제어권을 가진 함수가 callback의 this를 명시한 경우 그에 따른다.



