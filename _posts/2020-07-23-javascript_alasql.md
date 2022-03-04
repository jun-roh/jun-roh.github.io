---
layout: post
title:  "AlaSQL - Opensource SQL database"
summary: "AlaSQL - Opensource SQL database"
author: Jun Roh
date: '2020-07-23 14:35:23 +0530'
category: javascript
keywords: alasql, javascript, jquery database, javascript database, javascript query
permalink: /blog/alasql_javascript/
usemathjax: true
---

## AlaSQL  
&nbsp;

AlaSQL!! 발음은 ælæ 앨래 SQL? 이라고 하면 될것 같습니다.

AlaSQL은 무엇일까요?

AlaSQL은 관계형 데이터와 Schemaless 데이터의 쿼리 속도 및 데이터 소스 유연성에 중점을 둔 javascript 용 오픈소스 SQL 데이터베이스입니다.

AlaSQL에 대한 내용은 아래 자세히 설명 되어 있습니다.

[https://github.com/agershun/alasql](https://github.com/agershun/alasql)

라이브러리 설계 목적은 다음과 같습니다

-   BI 및 ERP Application을 위한 빠른 메모리 내 SQL 데이터 처리
    
-   간편한 ETL
    
-   모든 브라우저, Node.js 그리고 모바일 어플리케이션에서의 사용
    

사용하면서 가장 편하게 사용했던 내용은 API를 호출 해서 반환 받은 json 형식의 데이터 리스트를 원하는 조건, 값에 대해서 검색할 때 사용하니 쉽고 빠르게 원하는 데이터를 추출해 낼 수 있었습니다.

Excel, CSV, JSON, TAB, IndexedDB, LocalStorage, SQLite 형식의 파일을 사용할 수 있습니다.

사용 방법은 전형적으로 SQL 문법을 따르고 있습니다.

설치부터 어떤 방식으로 사용 가능한지 알아보도록 하겠습니다.

## 1\. 설치

### npm installation

"```"
yarn add alasql         # yarn
npm install alasql    # npm
npm install –g alasql    # global installation for command line tools
"```"

### CDN 이용

"```"
<script src="https://cdn.jsdelivr.net/npm/alasql@0.6"></script>
"```"

### Local Library 저장 사용

[https://github.com/agershun/alasql/tree/develop/dist](https://github.com/agershun/alasql/tree/develop/dist)

경로 : alasql/dist/alasql.js

## 2\. 데이터 세팅 및 사용

### 1) SQL Table

"```"
/* create SQL Table and add data */
alasql("CREATE TABLE cities (city string, pop number)");

/* Insert Data*/
alasql("INSERT INTO cities VALUES ('Paris',2249975),('Berlin',3517424),('Madrid',3041579)");

/* execute query */
var res1 = alasql("SELECT * FROM cities WHERE pop < 3500000 ORDER BY pop DESC");
"```"

### 2) Array Object

"```"
var data = [ {a: 1, b: 10}, {a: 2, b: 20}, {a: 1, b: 30} ];
var res2 = alasql('SELECT a, SUM(b) AS b FROM ? GROUP BY a',[data]);
"```"

### 3) Spreadsheet

"```"
alasql(['SELECT * FROM XLS("data/mydata") WHERE city = "London" '])
        .then(function(res){
            console.log(res);
        }).catch(function(err){
            console.log('Does the file exist? There was an error:', err);
        });
"```"

### 4) Bulk Data Load

"```"
alasql("CREATE TABLE example4 (a INT, b INT)");

// alasql's data store for a table can be assigned directly
alasql.tables.example4.data = [ {a:2,b:6}, {a:3,b:4} ];

// ... or manipulated with normal SQL
alasql("INSERT INTO example4 VALUES (1,5)");

var res = alasql("SELECT * FROM example4 ORDER BY b DESC");
"```"

### 5) Precompile Statements

"```"
var data = [{a:1},{a:2},{a:3},{a:4},{a:5}];

// Compile
var mysum = alasql.compile("SELECT VALUE SUM(a) FROM ? WHERE a > 2");

// Run
var res5 = mysum([data])
"```"

## 3\. Custom Function

"```"
/* Query에서 datetime 함수를 사용하기 위해서 custom 함수 생성 */
alasql.fn.datetime = function (param) {
    var origin_date = new Date((Date.parse(param)));
    var start_date = origin_date.getDate();start_date = start_date >= 10 ? start_date : '0' + start_date;var origin_month = (1 + origin_date.getMonth())origin_month = origin_month >= 10 ? origin_month : '0' + origin_month;var origin_time = origin_date.getHours();origin_time = origin_time >= 10 ? origin_time : '0' + origin_time;var origin_minute = origin_date.getMinutes();origin_minute = origin_minute >= 10 ? origin_minute : '0' + origin_minute;var origin_second = origin_date.getSeconds();origin_second = origin_second >= 10 ? origin_second : '0' + origin_second;result = origin_date.getFullYear() + "-" + origin_month + "-" + start_date + " " + origin_time + ":" + origin_minute + ":" + origin_second;
}

var res = alasql('SELECT datetime(’20200716’)’);
"```"

## 4\. 기본적으로 제공하는 Function

Custom 함수가 아니더라도 기본적으로 제공하는 함수들이 있습니다.

"```"
git clone https://github.com/agershun/alasql.wiki.git
"```"

기본적인 sql 문법을 제공하지만 Wiki 를 통해서 한번 더 제공되는 기능인지 확인 하신 후 사용하시기를 추천 드립니다.

[Sample Source\]

[https://github.com/jun-roh/AlaSQL-sample.git](https://github.com/jun-roh/AlaSQL-sample.git)