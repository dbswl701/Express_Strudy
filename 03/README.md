## 페이지 생성 구현
```js
app.get('/create', function(request, response){
  ......
      '<form action="/create_process" method="post">'
  ......
});

app.post('/create_process', function(request, response){...});
```
-> create에서 작성한 내용을 전송을 하면 create_process로 가는데 create_process는 method를 process방식으로 받는다.

이렇게 '/create', '/create_procdess'로 명시적으로 표시하기도 하지만 일반적으로는

```js
app.get('/create', function(request, response){
  ......
  '<form action="/create" method="post">'
  ......
});
app.post('/create', function(request, response){});
```
이렇게 하기도 한다.

접근할 때 get 방식으로 한다면 위에것에 걸리는 것이고, post방식으로 한다면 밑에것에 걸린다.

여기선 그냥 명시적으로 구분!

## 페이지 수정 구현

app.get이랑 app.post랑 잘 활용해서 


## 페이지 삭제
페이지 상세보기에서 
```js
// <form action="delete_process" method="post">
<form action="/delete_process" method="post">
```
/를 추가하여 최상위 path의 뒤에 붙여줄 수 있도록 해 주었다.

기존에 redireciton을 해주던 방식인 
```js
response.writeHead(302, {Location: `/`});
response.end();
```
이것 말고도 express에서는 redirection을 편리하게 해주는 기능을 제공해주고 있다.

nodejs express redirect

```js
response.redirect(`/');
```

기존에 nodejs수업에서 만들었던 예제를 express로 전환하는 작업을 했음.

router기능이 대부분.

어떤 웹프레임워크를 배우고 익히던 간에 제일 먼저 체크해야 할 것은 
1. 설치방법
2. 어떻게 route 하는가.
path별로 어떻게 응답하는가, get, post 방식으로 접속했을 때 어떻게 구분해서 그것을 응답하는가

// router 끝