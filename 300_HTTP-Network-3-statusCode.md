## 상태 코드

100 번대 : 리퀘스트를 받아들여 처리중

200 번대 : 리퀘스트를 정상적으로 처리했음

300 번대 : 리퀘스트를 완료하기 위해서 추가 동작이 필요

400 번대 : 서버는 리퀘스트 이해 불가능

500 번대 : 서버는 리퀘스트 처리 실패

### 200번 - 성공 (success)

클라이언트가 보낸 리퀘스트를 서버가 정상 처리 하였음을 나타낸다.

### 204번 - No Content

-리퀘스트를 성공했지만 돌려줄 리소스가 없을때

서버가 리퀘스트를 받아서 처리하는데는 성공했지만 리스폰스에 엔티티 바디를 포함하지 않는다. 204 리스폰스를 수신했어도 표시되어 있는 화면이 변하는 일은 없다. 이것은 서버에 정보를 보내는 것으로 족하고, 클라이언트에 대해서 새로운 정보를 보낼 필요가 없는 경우에 사용됨

### 206번 - Partial Content

-일부만 가지고 싶을때, 서버에서 일부만 돌려줄때

부분적 GET 리퀘스트를 받았음을 나타낸다. 리스폰스에 Content-Range로 지정된 범위의 엔티티가 포함되게 된다.

### 300번 - 리다이렉트(Redirection)

300번 리스폰스는 리퀘스트가 정상적으로 처리를 종료하기 위해 브라우저 측에서 특별한 처리를 수행해야 함을 나타낸다. 

클라이언트 -> 북마크를 변경할 필요가 있어. 서버 -> 그 uri 새것이 아닌데 북마크라든가 변경하지 않을래?

301이 발생하는 상황으로는 아래의 리퀘스트와 같이 디렉토리를 지정했을때에 마지막 부분에 /를 붙이는 것을 잊은 경우 등이 있다.

~~~
http://test.com/test
~~~

### 302 Found

이 리스폰스는 리퀘스트된 리소스에는 새로운 uri가 할당되어 있기 때문에 그 uri를 참조해 주길 바란다는 의미를 나타내고 있습니다.

ex) 북마크 하고 있는 경우에는 301의 경우와 같이 북마크를 변경하지 않고, 계속해서 302를 돌려준 페이지에 대해서 북마크 해야 한다.

### 303 See Other

-서버-> 그 uri새것으로 바뀌었어 잠시 그쪽으로 갈래?

### 304 Not Modified

-리소스는 있는데 조건이 안맞잖아

이 리스폰스는 클라이언트가 조건부 리퀘스트를 했을 때 리소스에 대한 액세스는 허락하지만, 조건이 충족되지 않음을 표시하고 있다. 304를 되돌려줄 경우에는 리스폰스 바디에 어떤 것도 포함되어 있어서는 안된다. 

304는 3xx에 분류되어 있지만 리다이렉트와는 관계가 없다.

### 307 Temporary Redirect

이 리스폰스는 302 Found와 같은 의미를 지니지만, 302의 경우에는 POST로 부터 GET으로 치환이 금지되어 있는데도 불구하고 구현상 그와 같이 되어 있지는 않다. 브라우저 마다 response하는 동작이 다를 수 있다.

### 400 클라이언트 에러(Client Error)

### 400 Bad Reqeust

-이 리퀘스트, 뭐지? 잘못된 거 아냐?

이 리스폰스는 리퀘스트 구문이 잘못되었음을 나타내고 있다. 이 에러가 발생한 경우, 리퀘스트 내용을 재검토하고 나서 재송신할 필요가 있다.

### 401 Unauthorized

이 리스폰스는 송신한 리퀘스트에 HTTP인증(BASIC 인증, DIGEST 인증)정보가 필요하다는 것을 나타내고 있다. 이미 1번 리퀘스트가 이루어진 경우에 유저 인증에 실패했음을 표시

### 403 Forbidden

이 리스폰스는 리퀘스트된 리소스의 액세스가 거부되었음을 나타내고 있다. 서버 측은 거부의 이유를 분명히 할 필요가 있는데, 이유를 명확하게 하는 경우에는 에니티 바디에 기재해서 유저 측에 표시한다.

403발생 원인으로 파일 시스템의 퍼미션이 부여되지 않은 경우 와 액세스 권한의 문제(허가되지 않은 송신 IP주소의 액세스 등)가 있는 것을 예로 들 수 있습니다.

### 404 Not Found

리퀘스트한 리소스는 서버에 없다는 것을 타나낸다. 또한 서버 측에 해당 리퀘스트를 거부하고 싶은 이유를 분명히 할때 이용할 수 있다.

### 500 서버 에러 (Server Error)

500리스폰스는 서버 원인으로 에러가 발생하고 있음을 나타낸다.

### 500 Internal Server Error

이 리스폰스는 서버에서 리퀘스트를 처리하는 도중에 에러가 발생하였음을 나타내고 있다. 웹 애플리케이션에 에러가 발생한 경우나 일시적인 경우도 있다.

### 503 Service Unavaliable

이 리스폰스는 일시적으로 서버가 과부하 상태이거나 점검중이기 때문에 현재 리퀘스트를 처리할 수 없음을 나타내고 있다. 

> **상태 코드가 현재 상황과 불일치할 수도 있다**
>
> 리스폰스로 되돌아오는 상태 코드의 대부분은 유저가 다른 내용을 알기 어렵게 되어있다. 흔히 있는 상황으로 웹 어플리케이션에서 애플리케이션 애러가 발생한 경우에도 상태 코드로 [200 OK]가 되돌아 오는 경우가 있다.