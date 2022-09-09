---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_CSS2
title: Reset-CSS, Comment, Vendor Prefix
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
date: 2022-09-08 17:12:30 +0900
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

## 1. 너무 많은 브라우저들과 각자 다른 스타일

- 브라우저 마다 제공하는 요소의 기본 스타일(User Agent Style)이 모두 다르다.

## 2. 에릭 마이어의 reset CSS

- 브라우저의 모든 기본적인 스타일 속성들을 초기화
- 2011년 이후 업데이트 중단
- [meyerweb.com](https://meyerweb.com/eric/tools/css/reset/)

복붙해서 사용

## 3. normailize.CSS

- 브라우저의 기본적 스타일 속성을 모두 제거하지 X
- 어떤 브라우저에서든 비슷하게 보이도록 정규화 (완전히 똑같이 만드는 것은 X)
- 브라우저 고유의 스타일을 존중하면서 거기에 스타일을 첨가하는 부드러운 방법
- 에릭 마이어의 reset CSS 보다 업데이트 되어 있음
- **가장 많이 사용**
- [normalize.css/normalize.css at master · necolas/normalize.css](https://github.com/necolas/normalize.css/blob/master/normalize.css)

## 4. CSS Remedy

- 차세대 CSS Reset 프로젝트
- 하위 브라우저 호환 걱정 없이 CSS가 브라우저에서 효율적으로 작동하도록 하는 것이 목표
- 프로젝트 진행 중

## 5. 공백처리

- css는 html과 마찬가지로 공백을 규합
- 따라서 아래 사항중 어떻게 사용해도 무방합니다.
- prettier 익스텐션 사용하면 다 같은 모양으로 정렬됨

```css
h1 {
  color: black;
}
h1 {
  color: black;
}
h1 {
  color: black;
}
h1 {
  border: solid 1px black;
}
h1 {
  border: solid 1px black;
}
h1 {
  border: solid 1px black;
}
```

## 6. 주석

```css
/* 주석 */
```

## 7. 벤더프리픽스 (**Vendor-Prefix**)

- 벤더(브라우저 제조사) + 프리픽스(접두어)
- 아직 비표준이거나 실험적인 CSS 속성을 특정 브라우저에서 실행할 수 있도록 CSS 속성 앞에 브라우저 제조사 만의 접두어(prefix)를 붙이는 문법

```css
**-webkit-**transition: all 4s ease;
**-moz-**transition: all 4s ease;
**-ms-**transition: all 4s ease;
**-o-**transition: all 4s ease;
transition: all 4s ease;
```

| 벤더 프리픽스 | 웹 브라우저                                                                 | 예                           |
| ------------- | --------------------------------------------------------------------------- | ---------------------------- |
| -webkit-      | 크롬, 안드로이드, 사파리, ios 기반 파이어폭스, 오페라 등 웹킷 기반 브라우저 | -webkit-transition: all .5s; |
| -moz-         | 파이어폭스 브라우저                                                         | -moz-transition: all .5s;    |
| -ms-          | 마이크로소프트 인터넷 익스플로러, 레거시 엣지                               | -ms-transition: all .5s;     |
| -o-           | 레거시 오페라 브라우저                                                      | -o-transition: all .5s;      |

<aside>
<strong>💡 웹킷 기반 브라우저?</strong><br>
웹킷(Webkit)은 브라우저가 HTML, CSS를 화면에 그려줄때 사용하는 렌더링 엔진입니다.
크롬, 안드로이드, 사파리, ios 기반 파이어폭스 등 많은 브라우저들이 사용했습니다. 
현재 크롬, 안드로이드, 오페라, 마이크로소프트 엣지 브라우저 등은 <strong>Blink</strong> 엔진으로 전환되었습니다. 
참고로 Blink 엔진은 vendor-prefix가 존재하지 않습니다.

</aside>

- 벤더 프리픽스는 줄어드는 중고 있습니다! 다행이도요! 익스플로러도 종료 예정이고요.
- 브라우저 몇 버전까지 호환을 해줄 것인가에 대한 회의가 필요

- [Autoprefixer CSS online](https://autoprefixer.github.io/)
