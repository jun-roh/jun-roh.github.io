---
layout: post
title:  "DataTables - Datatables 가 너무 느려요!!"
summary: DataTables - Datatables 가 너무 느려요!!
author: Jun
date: '2020-12-03 20:35:23 +0530'
category: javascript
use_math: false
thumbnail: /assets/img/thumbnail/keyboard.jpeg
---

## Datatables 가 너무 느려요!!

웹에서 Table 을 쉽게 다양한 기능을 넣어서 만들고 싶을때는 바로 DataTables 라이브러리를 사용합니!

#### [ DataTables URL ]

https://datatables.net/

귀찮은 페이징 처리도 해주고 searching, sorting 까지! 아주 다양한 기능을 제공해줍니.

다양한 기능은 물론, html table 태그로 테이블을 만들어 놓고 DaTables 를 호출하면 됩니다.

사이트에도 기본적으로 이렇게 나와 있을 것입니다.

사실은 다른 방법도 있는데 귀찮아서 이렇게 개발을 해보았습니다!

하지만 문제가 발생하기 시작했습니다!

테이블의 크기가 커지면 커질수록 느려지기 시작한 것 입니다.

이유는 테이블 row 가 많아지면 많아질수록 전체 테이블을 그리고 그 다음에 DataTables 에서 라이브러리에 맞게 렌더링을 합니다.

데이터가 만개 있을 경우에 그냥 테이블 그리는것도 힘든데 다시 또 렌더링까지... 브라우저가 죽지 않으면 다행입니다.

그렇다면 만개 데이터가 있을 경우 DataTables 는 사용할 수 없는 것일까요?

방법이 있습니다! 

Table 을 먼저 만들고 Rendering 하는 방법이 아닌 datatable 을 만들때 직접 데이터를 넣고 column을 세팅 하는 방법입니다.

참고할 사이트는 

