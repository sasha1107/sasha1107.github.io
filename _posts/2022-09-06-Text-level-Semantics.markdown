---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_HTML4
title: Text-level Semantics

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
comments_disable: true

# publish date
date: 2022-09-06 16:49:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-09-12 13:45:08 +0900
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
#published: false
---

{%- comment -%} Please delete below and place your page content here {%- endcomment -%}

## 텍스트 레벨 요소 특징

- 컨텐츠의 크기 만큼만 영역 점유
- 자식으로 Sections, Grouping Contents를 배치할 수 없다.

## `<br>`

- 줄바꿈 태그

## `<wbr>`

- 텍스트 박스에서 한 줄로 모두 표시가 안될 때에만 줄바꿈이 일어나는 역할
- 문장이 너무 길어서 문장을 감싸는 부모 영역보다 길 때 줄바꿈이 일어나게 하는 역할

## `<a href=”경로”>`

- 하이퍼텍스트 → 링크를 만들 때 사용
- `href` 속성
  > hyper reference
  - 경로를 지정할 수 있음
  - href 속성을 사용하지 않고 자바스크립트로 경로를 지정할 수도 있다.
    - 하지만 웹 접근성에 위배되므로 href 속성 사용 권장
      - 웹 에이전트가 javascript를 읽지 않음(HTML 만 읽음)
    - 웹 표준에도 위배
      - 기본적으로 href 가 없으면 문법 에러
- 텍스트 레벨 요소이지만 예외적으로 sections, grouping content 요소를 자식으로 하는것을 허용
- `<a>` 요소안의 자식으로는 `<a>` 요소나 `<button>` 과 같이 사용자와 인터렉션이 가능한 요소를 자식으로 두지 않음

```html
<a href="https://www.naver.com">click</a>

<!-- 새 탭으로 열기 -->
<a href="https://www.naver.com" target="_blank">click</a>

<!-- 현재 디렉토리 안에서 index.html을 열기 -->
<a href="./index.html">click</a>

<!-- 해쉬 링크(페이지 안에서 이동하고 싶을 때 사용(id만 가능, 클래스 불가) 예.페이지 상단이동, 목차 이동) -->
<a href="#three">click</a>

<!-- 다운로드 -->
<a href="./index.html" download>click</a>

<!-- 해당 경로에 파일이 있다면 브라우저에서 파일 오픈 -->
<a href="./hello.hwp">hwp click</a>
<a href="./hello.pdf">pdf click</a>
이런거는 경로에 해당 파일이 존재하면 브라우저에서 파일이 열리나요?

<!-- 파일명을 "a.hwp/a.pdf"로 다운로드 하겠다 -->
<a href="./hello.hwp" download="a.hwp">hwp download click</a>
<a href="./hello.pdf" download="a.pdf">pdf download click</a>

<!-- 전화 걸기 -->
<a href="tel:+82027777777">(02)777-7777</a>

<!-- 메일 -->
<a href="mailto:hello@gmail.com">hello@gmail.com</a>
```

<aside>
❌ IE에서는 `download` 속성 지원 X

</aside>
<br>

## `<b>` - 사용 권장 X

- bold
- 텍스트를 굵게 표시
- 의미가 없음 → 시멘틱하지 않음(시멘틱 태그 나오기 전 있던 태그)
- 더 이상 사용하지 X

<br>

## `<strong>`

- 굵은 글꼴 + 중요도 → 강조
- 중요도를 더 강조하고 싶을 때 strong을 중첩하여 사용하기도 함
- h1~h6 쓰기 애매한 경우 제목을 지정할 때 사용하기도 함.

<br>

## `<i>`

- italic
- 기울임 글꼴
- HTML5에서 의미가 생김
  - 전문용어
  - 문단에서 주언어와 다른 언어로 표현된 부분
    - 주 언어가 한글이지만 영어로 표기되었을 경우
  - 어떤 이유로 주위와 구분해야 하는 부분 등
    - 예) 소설 속 등장인물의 생각

<br>

## `<em>`

- emphasize
- `<i>`와 같은 기울임 글꼴
- 강조의 의미 (`<strong>` 보다는 약한 강조)

<br>

## `<dfn>`

- define
- 용어 정의
  - 문서에서 최초로 나타났을 때 사용합니다. (1번)
- `<dl>` + `<dt>` 사용하고 싶지만 목록이 아닌 경우(1~2개)
- dfn의 가장 가까운 부모가 `<p>` 혹은 `<dt><dd>` 쌍, `<section>` 요소일 경우 그 컨텐츠를 dfn의 정의에 대한 설명으로 간주합니다.

<br>

## `<abbr>`

- 준말, 약자
- 보통 홀로 쓰이고 dfn 태그로 감싸주기도 함
- title 속성
  - 요소에 대한 제목을 붙여주고 싶을 때

```html
<dl>
  <dt>WWW</dt>
  <dd>
    <dfn><abbr title="World Wide Web">WWW</abbr></dfn
    >는 인터넷에 연결된 컴퓨터를 통해 사람들이 정보를 공유할 수 있는 전 세계적인
    정보 공간을 말한다. - 위키백과
  </dd>
</dl>
```

<br>

## `<sup>`, `<sub>`

- `<sup>`
  - 윗첨자
- `<sub>`
  - 아랫첨자
- 화학 기호나 수학 공식 등 첨자 기호에 사용

```html
<p>H<sub>2</sub>0</p>
<p>x<sup>2</sup>=4</p>
```

<br>

## `<span>`

- 별다른 의미가 없음
- 보통 줄바꿈없이 영역을 묶는 용도로 사용
  - div와 목적이 동일
  - div(블록 레벨)는 줄바꿈 되고, span(텍스트 레벨)은 되지 않는다.
  - 둘 다 최후 수단으로 사용하기!
- 여러 요소를 묶어 컨트롤하기 위한 영역으로 id class를 사용하기도 함

```html
...중략...
<style>
  #명언 {
    color: red;
  }
</style>
...중략...
<p>
  <span id="명언">제발 그만해.. 이러다 다~~ 죽어!</span>라고 오일남이
  소리쳤습니다.
</p>
<p></p>
```
