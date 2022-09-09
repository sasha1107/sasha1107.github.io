---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_CSS3
title: CSS Selector, Selector Priority

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
#author: Soohyun Jung
# multiple category is not supported
category: HTML&CSS
# multiple tag entries are possible
tags: [CSS]
# thumbnail image for post
img: ":post_pic3.jpg"
# disable comments on this page
#comments_disable: true

# publish date
date: 2022-09-09 22:09:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2022-01-01 10:04:30 +0900
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

## 1. 전체 **선택자 (Universal Selector)**

- 문서 전체에 공통적으로 값을 지정
- 전체 선택자는 `*` (에스터리스크)을 사용

```css
* {
  margin: 0 auto;
}
```

## 2. 타입 **선택자 (Type Selector)**

- 태그 이름 지정
- 모든 해당 태그에 속성을 적용합니다.

```css
p {
  color: red;
}
```

## 3. 아이디 선택자 (ID Selector)

- **id 속성**
  - 문서 내에서 유일 → 해당 요소를 유일하게 식별할 때 사용
  - 한 요소에서 id를 중복해서 사용할 수 없음
    ```html
    <!-- id는 불가 -->
    <div id="one two three">
      <!--class는 가능-->
      <div class="one two three"></div>
    </div>
    ```
- id 이름 컨벤션
  - ‘`_`’ (언더바), ‘`-`’(하이픈)으로 시작
  - css에서 캐멀케이스는 쓰지 않음
- id 선택자
  - `#`
    ```css
    #blue {
      color: blue;
    }
    ```
- id 속성을 이용하면 **해쉬 링크**를 만들 수 있다.
  - `<a href="#id>`
  - 다른 페이지로 이동하는 링크가 아닌 현재 페이지에서 이동

## 4. 클래스 선택자 (Class Selector)

- id 속성과 마찬가지로 해당 요소를 식별할 때 사용
  | id 속성 | class 속성 |
  | ------------------- | -------------------------- |
  | 한 페이지에 하나만 | 한 페이지에 여러개 가능 |
  | 한 태그에 한 아이디 | 한 태그에 여러 클래스 가능 |
- class 명 컨벤션
  - 알파벳 또는 ‘\_’ (언더바), ‘-’(하이픈)으로 시작
  - 직관적, 간단명료

```css
.red {
	color: blue;
}

/* 클래스 중복 가능 */
<p class="one two three">
```

## 5. 선택자 목록 (**[Selector list](https://developer.mozilla.org/en-US/docs/Web/CSS/Selector_list)**)

- 여러 선택자 같이 스타일 지정
- 콤마 `,` 로 선택자를 연결

```css
h1 {
  color: red;
}
h2 {
  color: red;
}
h3 {
  color: red;
}

h1,
h2,
h3 {
  color: red;
}
```

---

## 6. 선택자 우선순위의 3가지 원칙

- 6.1 후자 우선의 원칙
- 6.2 구체성의 원칙
- 6.3 중요성의 원칙

## 6.1 후자 우선의 원칙

- 동일한 선택자가 연속으로 사용되었을 경우 후자가 우선합니다.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <style>
      p {
        color: red;
        font-size: 20px;
      }

      p {
        color: green;
      }
    </style>
  </head>

  <body>
    <p>
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Qui, dolor
      voluptatem inventore deleniti eligendi omnis corporis iste adipisci
      consectetur ad officia quasi, doloribus fuga? Expedita error ad sunt
      reiciendis sapiente.
    </p>
  </body>
</html>
```

- p의 color가 green으로 덮어씌워짐

## 6.2 구체성(Specificity)의 원칙

- Specificity → 특이성/명시도/구체성
- 더 구체적으로 작성된 선택자가 우선한다.

```html
<head>
  <style>
    p.color-red {
      color: red;
      font-size: 20px;
    }

    p {
      color: green;
    }
  </style>
</head>

<body>
  <p class="color-red">
    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Praesentium, dolor
    repudiandae tempora consequatur maxime animi ad! Quibusdam beatae laudantium
    itaque eos, cupiditate vero reiciendis assumenda natus reprehenderit eveniet
    at enim?
  </p>
</body>
```

→ `p` < `p.color-red` 더 구체적이므로 우선됨!

### 6.2.1 가중치

- 구체적인 정도를 판단하는 수치

<aside>
<strong>⚠️ 가중치 비교</strong><br>
id > class > 타입

</aside>
<br>

### 6.2.2 우선 순위 계산

- 가중치 점수가 있어 이를 기반으로 우선순위를 계산

| 선택자                        | 가중치 점수 |
| ----------------------------- | ----------- |
| inline-style                  | 1000점      |
| id 선택자                     | 100점       |
| class, 가상클래스, 속성선택자 | 10점        |
| 타입, 가상요소 선택자         | 1점         |
| 전체선택자 ( \* )             | 0점         |

- 같은 점수 일때?
  - 클래스 선택자가 아무리 많더라고 하더라도 아이디 선택자를 넘어가지 못함
    - class 10개 < id 1개
    - class 100개 < id 1개
- 가중치 계산 사이트
  [Specificity Calculator](https://specificity.keegan.st/)

## 6.3 중요성의 원칙

- `!important`
  - 절대적인 우선순위.
  - 가중치 점수를 무시하고 무조건적인 우선 순위
  - 사용 자제
  - inline css 보다 우선!

```css
.one {
  color: red !important;
}
```
