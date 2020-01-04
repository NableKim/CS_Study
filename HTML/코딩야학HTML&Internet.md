# HTML & Internet

## 목차
- 코딩과 HTML



## 코딩과 HTML

  - 화면이 두 개로 쪼개져 있다. Point는 어떤 쪽이 사람이 하는 일이고, 어떤 쪽이 기계가 하는 것인가를 분리해서 생각해보는 것이다.
  - ![기계VS사람](./images/기계VS사람.PNG)
  
  - 오른쪽이 사람이 하는 일이면서 원인이고, 왼쪽은 사람이 하는 일에 대한 결과이면서 기계가 한 일입니다.
  - 오른쪽을 신호라는 의미에서 Code, 원천에서 의미에서 Source, 약속의 의미에서 Language 라고 합니다.
  - 왼쪽은 결과를 부르는 여러 표현들이 있다. (Application, App, Program, Webpage, Website) 
  - **코딩** : **원인인 Code를 통해서 결과인 Website 를 만들어내는 것**
  - ex) HTML 언어를 사용하여 웹 사이트를 만들어내는 것
  
  
## Public Domain

- 저작권이 없는 것 
- ex) 한글을 사용할 때 라이센스 비용 지불하지 않음, HTML
- 덕분에 NAVER, GOOGLE 에서 각각의 브라우저를 만들 수 있음



## HTML 태그 예제

```html
<p>hello this is <strong>cgin</strong>! <u>nice to meet you~</u></p>

```

- <strong> 태그 : 강하게
- <u> 태그 : 밑줄


## HTML 줄바꿈 태그

- <br> : 닫는 태그가 따로 없음 -> 의미가 없다. 단지 줄바꿈이다!
- <p></p> : 정보로써 한 단락을 의미하는 태그 -> 정보로써 한 단락을 의미한다.



## CSS 속성

- margin

```css
<p style="margin-top:40px"></p> // 위에 40px의 여백을 준다.


```

- 의미에 맡는 html 태그를 사용하는 것이 중요한것이다. css는 그냥 꾸며주는 것이다!



## HTML img 속성

```html

<img src="coding.jpg" width="100%">

```
- 'src', 'width' : 속성(attribte)
- 속성의 위치는 상관 X



## 부모 자식 태그, 목차

- 목차
  ```html
  
  <li>html</li>
  <li>css</li>
  <li>javascript</li>

  ```

   ```html
  <ul>
    <li>html</li>
    <li>css</li>
    <li>javascript</li>
  </ul>
  ```
  
  - <li>태그는 부모 태그로 <ul> 태그를 가지고 있다.
  - <ol> : Ordered List
  - <ul> : Unordered List
  
  
  ```html
  
  <table>
    <tr>
      <td>1</td>
      <td>2</td>
    </tr>
  </table>
  
  ```
  
  
  - <table>은 3대가 같이 다닌다. 
  - <table> 할아버지, <tr> 아버지, <td> 아들




## 문서의 구조

- 컴퓨터는 0과 1만 인식을 한다.
  ```html
  <h1>안녕!</h1>
  ```
  
  - 해당 html를 실행하면 한글을 인식을 못한다.

  ```html
  <meta charset="utf-8">
  ```

  - 인식을 못한 이유는 우리가 작성을 utf-8 문서형식으로 작성을 하였는 데 컴퓨터는 지금 utf-8형식을 읽지 않았기 때문이다.



## a태그

- HyperText
- <a></a> : 링크
- 해당 링크가 없다면 우리는 포털사이트에서 검색을 사용할 수 없다.






