## call back function

호출하다. 다시 돌려주다(리턴의 의미). 호출해서 돌려줄 함수.

이 함수를 호출해서 그결과를 나한테 알려줘, 걱정마 내가 알아내서 줄게,

제어권을 맡긴다. 

### 제어권

**실행시점**

setInterval - 주기적으로 실행해라 , 1인자 : 콜백함수, 2인자: 주기)  
setInterval( callback, milliseconds );

**인자**

forEach에서 두번째 인수로 thisArg를 생략하고있다.

### 특징

1. 다른함수의 A인자로 콜백함수 B를 전달하면 A가 B의 제어권을 갖게된다

2. 특별한 요청(this)가 없는 한 A에 미리정해놓은 방식에 따라 B를 호출한다

3. 미리 정해놓은 방식이란 어떤시점에 콜백을 호출할지 인자에는 어떤 값들을 지정할지  THIS에 무엇을 바인딩할지 등이다.

### 주의

1. 콜백은 함수이다.