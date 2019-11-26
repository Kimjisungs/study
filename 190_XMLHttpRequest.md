## XMLHttpRequest

ajax 요청 및 생성.

~~~javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', '/todos');
//xhr.open('GET', 'http://localhost:3000/todos');
xhr.sand();
~~~

**xhr.open** ('GET', '/todos')   

1. 첫번째 인수로 메소드, 두번째는 루트 경로이다.
2. ajax통신하기 위한 준비단계이다.

**xhr.sand()**  

1. playload가 있으면 안에다 playload를 주고 없으면 이대로 둔다.

~~~javascript
xhr.onreadystatechange = () => {
	if (xhr.readyState !== XMLHttpRequest.DONE) return
     if (xhr.status === 200) {
         
      console.log(typeof JSON.parse(xhr.response))
      console.log(JSON.parse(xhr.response))
      todos = JSON.parse(xhr.response);
      render();
         
    } else {
      console.error('Error', xhr.status, xhr.statusText);
    }
}
~~~

**xhr.onreadystatechange** = () =>   

1. 여기서 response를 받고, 무조건 비동기로 처리한다.
2. 이벤트를 채킹하면 발생하고 무한 루프로 체크한다.
3. 비동기 함수 콜백은 tesk que에 들어간다. 

**if (xhr.readyState !== XMLHttpReqeust.DONE) return;**

1. 응답 받지 않은 상태이면 계속 기다린다.
2. xhr.readyState 변화하는데 0번에서 4번까지 순차적으로 변함

| Value | State            | Description                                           |
| :---: | :--------------- | :---------------------------------------------------- |
|   0   | UNSENT           | XMLHttpRequest.open() 메소드 호출 이전                |
|   1   | OPENED           | XMLHttpRequest.open() 메소드 호출 완료                |
|   2   | HEADERS_RECEIVED | XMLHttpRequest.send() 메소드 호출 완료                |
|   3   | LOADING          | 서버 응답 중(XMLHttpRequest.responseText 미완성 상태) |
|   4   | DONE             | 서버 응답 완료                                        |

**if(xhr.status === 200)**  

1. 응답코드. 200번은 성공.  구글에 http status code치면 코드 번호에 따른 결과가 나온다.

**else { console.log(Error, xhr.status, xhr.statusText)}**  

1. error코드일경우 에러 번호를 알려주고, 내용을 알려준다.

**성공했을때 if문 안에 **

**xhr.response** 

1. 백엔드에서 데이터가 담겨온다. string type으로 온다. 

**JSON.parse()**

1. JSON.parse(xhr.resopnse)를 string타입으로 받을때 객체로 변환해 준다. 
2.  todos = JSON.parse(xhr.response);
3.  render()는 이 이후에 해준다.