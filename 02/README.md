다시 정리

queryString으로, /?id=HTML에서 HTMl을 가져오는 것 보다
/page/HTML으로 접근했을 때 HTML을 가져오는 것으로 구현해보자(보기좋음. )

callback 함수 안에서 html을 가져와야 함.
route parameters

app.get('/page/:pageID')
```js
app.get('/page/:pageId', function(request, response){
  response.send(request.params)
});
```
page 뒤에 어떤 값이 들어오면 그걸 pageID라고 이름을 붙인것.

url path를 통해 parameter를 전달하는 경우 express에서 어떻게 처리하는지에 대해서 살펴봄

---

이전시간에 url에 queryString이 아닌 path 방식을 통해서 parameter가 전달되는 경우에 처리하는 방법을 살펴봄
이번시간에는 구현!
```js
// var filteredId = path.parse(queryData.id).base;
var filteredId = path.parse(request.params.pageId).base;
```
이거 queryString을 사용 안하니까 request.params.pageId 사용

template.js안에서 
      list = list + `<li><a href="/page/ ${filelist[i]}">${filelist[i]}</a></li>`;

이거 /?id=에서 page/로 바꿈

이렇게 해서 상세보기 페이지를 구현하는 방법을 살펴보았고, 이 구현에서 가장 중요한 부분은 url path 방식으로 파라미터를 전달하는 것을 처리하는 라우팅 기법을 살펴보았다.