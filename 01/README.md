## express 설치

https://expressjs.com/ko/

```js
npm install express --save
```
package manager인 npm을 이용해서 express라고 하는 module을 local에 save

다운이 끝나면 node_modules안에 express가 추가된다.

어떻게 쓰는가에 대한 것은 getting started 확인


```js
// express도 모듈이기에 module을 load 해오는 코드 
// const(상수) : 바뀌지 않는다.
const express = require('express')

// express는 함수. 밑에 보면 함수처럼 호출하고 있다.
// return 되는 값은 app에 담기는데, applicaiton이라는 객체가 담기도록 약속되어 있다.
const app = express()
const port = 3000

// route. routing
// app.get(path, callback [, callback ...])
// app.get('/', (req, res) => {
//   res.send('Hello World!')
// })
app.get('/', function(req, res){
  return res.send('/')
});

app.get('/page', function(req, res){
  return res.send('/page')
});


// app.listen(port, () => {
//   console.log(`Example app listening at http://localhost:${port}`)
// })
app.listen(3000, function(){
  console.log('Example app listening on port 3000!');
});
```


rounte. routing.
사용자들이 여러가지 path를 통해서 들어올 때 path마다 적당한 응답 필요

/ -> /실행
/page -> /page 실행

app.get이라는 method를 호출하고 그 method의 첫번째 인자로 path를 전달하는것을 통해서 routing을 하고 있다.
우리가 가지고 있던 기존의 코드에서는 routing을 뭘 통해 했냐면 if문들 통해서 pathname이 /인 경우에는 ~~
create인 경우에는 ~~~ 이 실행되도록 하게 해서 routing을 구현하였다.

이전 방식에 비해 이 방식이 가독성이 훨씬 더 좋고 깔끔하다.

```js
app.listen(3000, function(){
  console.log('Example app listening on port 3000!');
});
```
applicaiton객체의 listen메소드의 첫번째 인자로 3000을 주면 저 listen이라는 method가 실행될 때 비로소 웹서버가 실행이 되면서 3000번 port에 listen이 가게되고, 그 listen이 성공하게 되면 callback 함수가 실행된다. 
이 코드는 기존 코드에 제일 밑에 있엇던 app.listen(3000); 과 동일하다.

---

## 홈페이지 구현
    response.writeHead(200);
    response.end(html);

    이거를 이렇게 한번에 가능

        response.send(html);

내일 정리하자
