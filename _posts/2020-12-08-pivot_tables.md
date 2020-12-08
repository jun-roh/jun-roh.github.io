---
layout: post
title:  "Pivot Table using javascript"
summary: Pivot Table using javascript
author: Jun
date: '2020-12-08 20:35:23 +0530'
category: javascript
use_math: false
thumbnail: /assets/img/thumbnail/keyboard.jpeg
---

## pivot table 만들기 (html, javascript)

javascript 라이브러리를 활용해서 pivot table 을 만들기 위한 라이브러리 소개 해보겠습니다.

javascript 용 pivot table 라이브러리는 다양한 곳에서 제공하고 있습니다.

* Google Developers API
  *  <https://developers.google.com/sheets/api/guides/pivot-tables>
* PivotTables.js
    * <https://pivottable.js.org/examples/>
* Pivot.js
    * <https://rwjblue.github.io/pivot.js/>
    
등등 많은 곳에서 오픈 라이브러리로 제공하고 있습니다.

하지만 모든 라이브러리에서 저의 요구사항에 맞는 기능을 제공하지는 않았습니다.

1. 열, 행의 값이 복수로 들어가야함
    - 대부분의 라이브러리에서는 이 부분을 충족해주지는 않습니다.
    - 전체 라이브리에서 Aggregation 값에 대해서는 복수로 받고 열을 복수로 받는 소수의 라이브러리도 있었지만 행을 복수로 받는 라이브러리는 없었다.

2. 행의 sub_total 값을 계산해서 row 에 추가
    - 행의 값에 여러개 넣을 경우 제일 앞에 묶음으로 sub total 을 넣고 싶었습니다.
   
3. Custom 하게 cell 의 Format 을 변경하고 싶다
    - setting 값에 따라서 aggregation format 을 변경하고 싶었다.
    
위에 세가지 조건에 전체적으로 검토해 보았을때 Open 라이브러리에서는 사용하기 힘들어보였습니다.

그래서 Table 을 쉽게 만들어주는 datatables 와 pivot 계산을 하기 위한 alasql 이라는 javascript 라이브러리를 활용해서 pivot table 을 만들어보았다.

지속적으로 개발 중이므로 참고 부탁드립니다.

결과물은 다음과 같습니다.

![Image of pivot_table](/assets/img/thumbnail/pivot_table.png)

참고 하실 Source code 는 다음과 같습니다.

#### [ Github ]
<https://github.com/jun-roh/pivot-table-js>

질문이나 버그들은 알려주신다면 더욱 발전하는 저장소가 될 것입니다!