---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_HTML5
title: Tabular Data

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
#author: ""
# multiple category is not supported
category: HTML&CSS
# multiple tag entries are possible
tags: [HTML]
# thumbnail image for post
img: ":post_pic3.jpg"
# disable comments on this page
#comments_disable: true

# publish date
date: 2022-09-08 16:55:03 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-10-15 19:20:03 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# if you enabled image_viewer_posts you don't need to enable this. This is only if image_viewer_posts = false
#image_viewer_on: true
# if you enabled image_lazy_loader_posts you don't need to enable this. This is only if image_lazy_loader_posts = false
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: true
---

## Emmet 문법으로 테이블 만들기

- 7열 4행 테이블
  <img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/d3fefb3c-d3a8-4393-81b4-ee4562ce87ca/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220908%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220908T074820Z&X-Amz-Expires=86400&X-Amz-Signature=ff1b53826f95ea0f9e5de07782cb620a1e4ce5c4344d2e9d4ed4a2addcf059ce&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject" width="400px">

## `<table>`

- 테이블 생성

### table의 마크업 구조도

![스크린샷 2022-02-25 오후 12.59.33.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/cca0db6d-558a-4310-88f3-791691fbc1ce/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2022-02-25_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_12.59.33.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220908%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220908T074849Z&X-Amz-Expires=86400&X-Amz-Signature=0b0e1ac70607cbc1ed1921e854e4f1766a7edb26ed7b88aa6502fd730cc0fa83&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA%25202022-02-25%2520%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE%252012.59.33.png%22&x-id=GetObject)

## `<caption>`

- 테이블의 제목이나 설명
- `<table>` 요소의 첫번째 자식으로 사용해야함

```html
<table>
  <caption>
    이달의 책 판매량
  </caption>
  <tr>
    <th>구분</th>
    <th>이름</th>
    <th>판매량</th>
  </tr>
</table>
```

## `<thead>, <tbody>, <tfoot>`

`<thead>`

- 머리글

`<tbody>`

- 본문

`<tfoot>`

- 바닥 글
- 이 요소들은 테이블의 레이아웃에 영향을 미치지 X
- 하지만 CSS를 사용하여 디자인의 스타일을 지정할 수 있습니다.

<br>

<aside>
⚠️ `thead`, `tbody`는 필수! `tfoot`은 선택 사항
`thead`, `tbody`가 없다면 동적 데이터를 받아오지 못할 수도 있음.

</aside>

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>Page Title</title>
    <style>
      table,
      tr,
      th,
      td {
        border: 1px solid black;
        border-collapse: collapse;
      }
    </style>
  </head>
  <body>
    <table>
      <thead>
        <tr>
          <th>구분</th>
          <th>이름</th>
          <th>판매량</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>해리포터</td>
          <td>100</td>
        </tr>
        <tr>
          <td>2</td>
          <td>헝거게임</td>
          <td>200</td>
        </tr>
        <tr>
          <td>3</td>
          <td>반지의제왕</td>
          <td>300</td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <td colspan="2">총 판매량</td>
          <td>600</td>
        </tr>
      </tfoot>
    </table>
  </body>
</html>
```

## `<tr>, <th>, <td>`

`<tr>`

- 테이블의 행을 나눌 때 사용

`<td>`

- `<tr>` 태그로 나눈 행에서 셀을 분리할 때 사용
- HTML 요소의 모든 종류(텍스트, 이미지, 목록, 테이블 등)를 포함할 수 있습니다.

`<th>`

- 행, 열의 머리말을 나타내는 데 사용
- 글씨를 굵게, 가운데 정렬

```html
<table>
  <caption>
    이달의 책 판매량
  </caption>
  <tr>
    <th>구분</th>
    <th>이름</th>
    <th>판매량</th>
  </tr>
  <tr>
    <td>1</td>
    <td>해리포터</td>
    <td>100</td>
  </tr>
</table>
```

## 열간/행간 병합 `colspan`, `rowspan` 속성

`<td>` 또는 `<th>` 태그 요소에 `colspan` 속성을 사용하면 열간 병합을 할 수 있습니다. 즉, 열과 열을 병합하기 때문에 가로 방향으로 셀들을 병합할 수 있습니다. 또한 `rowspan` 속성을 사용하면 행간 병합이 가능합니다. 즉, 행과 행을 병합하기 때문에 세로 방향으로 셀들을 병합할 수 있습니다. 이때 병합하고 싶은 셀의 개수를 지정해 줍니다.

```html
<table>
  <caption>
    이달의 책 판매량
  </caption>
  <tr>
    <th>구분</th>
    <th colspan="2">이름</th>
    <!-- <th>판매량</th> -->
  </tr>
  <tr>
    <td>1</td>
    <td>해리포터</td>
    <td rowspan="2">100</td>
  </tr>
  <tr>
    <td>1</td>
    <td>해리포터2</td>
    <!-- <td>100</td> -->
  </tr>
</table>
```

## `<colgroup>, <col>`

- column들을 선택해서 꾸밀 수 있다.

- `<colgroup>`과 그 자식 요소로 쓰이는 `<col>` 요소를 통해 한 열에 공통적인 스타일을 주는 것도 가능

- `<colgroup>` 안의 `<col>` 요소는 각각 테이블의 ‘열’을 의미

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>Page Title</title>
    <style>
      table {
        width: 100%;
      }
      table,
      tr,
      th,
      td {
        border: 1px solid black;
        border-collapse: collapse;
      }
      .구분 {
        width: 20%;
      }
      .이름 {
        width: 50%;
      }
      .판매량 {
        width: 20%;
      }
    </style>
  </head>
  <body>
    <table>
      <caption>
        이 table은 영국에서 최초로 시작되어 일년에 한바퀴 돌면서...
      </caption>
      <colgroup>
        <col class="구분" />
        <col class="이름" />
        <col class="판매량" />
      </colgroup>
      <thead>
        <tr>
          <th>구분</th>
          <th>이름</th>
          <th>판매량</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>해리포터</td>
          <td>100</td>
        </tr>
        <tr>
          <td>2</td>
          <td>헝거게임</td>
          <td>200</td>
        </tr>
        <tr>
          <td>3</td>
          <td>반지의제왕</td>
          <td>300</td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <td colspan="2">총 판매량</td>
          <td>600</td>
        </tr>
      </tfoot>
    </table>
  </body>
</html>
```

## `scope`

- 데이터의 흐름

- 스크린리더기에서 읽는 방향을 지정해주는 역할을 함

- `<th>` 요소에 `scope` 속성을 사용해 `<td>` 와의 연결 관계를 설정 할 수 있다.

- row : 행 방향 진행
- col : 열 방행 진행

**`scope` 속성을 이용한 수평, 수직 테이블의 구현**

```html
<!-- 직접 구현하여 결과를 확인해 보세요 -->
<table>
  <caption>
    요일별 급식 만족도
  </caption>
  <tbody>
    <tr>
      <th></th>
      <th scope="col">월요일</th>
      <th scope="col">화요일</th>
      <th scope="col">수요일</th>
      <th scope="col">목요일</th>
      <th scope="col">금요일</th>
      <th scope="col">토요일</th>
    </tr>
    <tr>
      <th scope="row">메뉴</th>
      <td>돈까스</td>
      <td>짜장면</td>
      <td>볶음밥</td>
      <td>해물라면</td>
      <td>잔치국수</td>
      <td>떡볶이</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th scope="row">만족도</th>
      <td>3/5</td>
      <td>4/5</td>
      <td>1/5</td>
      <td>5/5</td>
      <td>2/5</td>
      <td>3/5</td>
    </tr>
  </tfoot>
</table>
```

- scope, colgroup에 대한 보강 설명

  [`<colgroup>` - HTML: Hypertext Markup Language | MDN](https://developer.mozilla.org/ko/docs/Web/HTML/Element/colgroup)

  [`<table>` - HTML: Hypertext Markup Language | MDN](https://developer.mozilla.org/ko/docs/Web/HTML/Element/table#%ED%96%89%EA%B3%BC_%EC%97%B4_%EB%B2%94%EC%9C%84_%EC%A7%80%EC%A0%95)
