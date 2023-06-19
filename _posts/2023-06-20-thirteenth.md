---
layout: single
title: "#5 Spring Framework Mybatis 게시판 만들기"
categories: SpringFramework
tag: [Spring, Spring Framework, Legacy, Mybatis, Board]
toc: true
toc_sticky: true
toc_label: "Spring Framework Mybatis 게시판 만들기"
author_profile: false
sidebar:
  nav: "docs"
---

## 1. 게시판 테이블 및 VO 생성

```xml
CREATE TABLE board (
    seq     NUMBER(5) PRIMARY KEY,
    title   VARCHAR2(210),
    writer  VARCHAR2(21),
    content VARCHAR2(2000),
    regdate DATE DEFAULT sysdate,
    cnt     NUMBER(5) DEFAULT 0
);
```

```java
@Getter 
@Setter
@ToString
@Builder
@NoArgsConstructor
public class Board {
	private int seq;
	private String title;
	private String writer;
	private String content;
	private Date regDate = new Date();
	private int cnt;
	private MultipartFile uploadFile;
	private String searchCondition;
	private String searchKeyword;
}
```
