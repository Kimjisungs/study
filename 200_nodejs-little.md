## Node 설정

**pakage.json **  
오픈소스 사용하는것을 관리  
명령어 : npm init -y  

**Express 설치**  
명령어 : npm install express   
팀원 : npm install

## Express - node.js 프레임워크

~~~javascript
const express = require('express');
const app = express(); //일반 함수이다.
~~~

1. require('express')는 node모듈에 가서 express패키지를 가지고 온다.
2. nodejs 모듈은 파일개념이어서 스코프를 갖는다.

~~~javascript
app.listen(3000, () => {  
  console.log('Server listening on port 7000');
})
~~~

1. 로컬 서버 실행   
   node app, nodemon app(package.json에 설정했을때)
2. app.listen(포트번호, 콜백함수);

~~~javascript
app.use(express.static('public'));
~~~

